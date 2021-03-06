---
title: Conector SQL Azure y Microsoft SQL graph para Microsoft Search
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configure el conector de Azure SQL y Microsoft SQL Graph para Microsoft Search.
ms.openlocfilehash: 499c0fad93f97e634086ff9025d947c4f70336fb
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508908"
---
<!---Previous ms.author: vivg --->

# <a name="azure-sql-and-microsoft-sql-server-graph-connectors"></a>Conectores SQL Azure y Microsoft SQL graph de servidor

El servidor de Microsoft SQL o el conector de Azure SQL Graph permiten a la organización detectar e indizar datos de una base de datos SQL Server local o una base de datos hospedada en la instancia de Azure SQL en la nube.
El conector graph indexa el contenido especificado en Microsoft Search. Para mantener el índice actualizado con los datos de origen, admite rastreos incrementales e completos periódicos. Con estos SQL, también puede restringir el acceso a los resultados de búsqueda para determinados usuarios.

> [!NOTE]
> Lea el [**artículo Configurar el conector de Graph**](configure-connector.md) para comprender las instrucciones generales de configuración de conectores de Graph.

Este artículo está dirigido a cualquier persona que configure, ejecute y monitore un conector de Azure SQL y Microsoft SQL graph de servidor. Complementa el proceso de configuración general y muestra instrucciones que se aplican solo para el conector de Graph SQL y Microsoft SQL servidor. En este artículo también se incluye [información](#limitations) sobre las limitaciones para el servidor de Microsoft SQL y los conectores SQL Azure.

## <a name="before-you-get-started"></a>Antes de empezar

### <a name="install-the-graph-connector-agent-required-for-on-premises-microsoft-sql-server-connector-only"></a>Instalar el agente de conector de Graph (necesario para el conector de servidor de Microsoft SQL local)

Para tener acceso a los datos de terceros locales, debe instalar y configurar el agente de conector de Graph. Consulte [Instalar el agente de conector de Graph](on-prem-agent.md) para obtener más información.  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Paso 1: Agregar un conector de Graph en el Centro de administración de Microsoft 365

Siga las instrucciones [generales de configuración](https://docs.microsoft.com/microsoftsearch/configure-connector).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a>Paso 2: Nombrar la conexión

Siga las instrucciones [generales de configuración](https://docs.microsoft.com/microsoftsearch/configure-connector).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Paso 3: Configurar las opciones de conexión

### <a name="register-an-app-for-azure-sql-connector-only"></a>Registrar una aplicación (solo para azure SQL conector)

Para el conector SQL azure, debe registrar una aplicación en Azure Active Directory para permitir que la aplicación de Búsqueda de Microsoft acceda a los datos para la indización. Para obtener más información sobre cómo registrar una aplicación, consulte la documentación de Microsoft Graph sobre cómo [registrar una aplicación](https://docs.microsoft.com/graph/auth-register-app-v2).

Después de completar el registro de la aplicación y tomar nota del nombre de la aplicación, el identificador de la aplicación (cliente) y el identificador de inquilino, debe generar [un nuevo secreto de cliente](https://docs.microsoft.com/azure/healthcare-apis/register-confidential-azure-ad-client-app#application-secret). El secreto de cliente solo se mostrará una vez. Recuerde tener en cuenta & almacenar el secreto de cliente de forma segura. Use el identificador de cliente y el secreto de cliente al configurar una nueva conexión en Microsoft Search.

Para agregar la aplicación registrada a la base de datos SQL Azure, debe:

- Inicie sesión en su base de datos SQL Azure
- Abrir una nueva ventana de consulta
- Para crear un usuario nuevo, ejecute el comando 'CREATE USER [app name] FROM EXTERNAL PROVIDER'
- Agregar usuario al rol ejecutando el comando 'exec sp_addrolemember 'db_datareader', [nombre de la aplicación]' O 'ALTER ROLE db_datareader ADD MEMBER [nombre de la aplicación]'

>[!NOTE]
>Para revocar el acceso a cualquier aplicación registrada en Azure Active Directory, consulte la documentación de Azure sobre [cómo quitar una aplicación registrada.](https://docs.microsoft.com/azure/active-directory/develop/quickstart-remove-app)

### <a name="connection-settings"></a>Configuración de conexión

Para conectar el conector de servidor de Microsoft SQL a un origen de datos, debe configurar el servidor de base de datos que desea rastrear y el agente local. A continuación, puede conectarse a la base de datos con el método de autenticación necesario.

> [!NOTE] 
> La base de datos debe SQL versión 2008 o posterior para que el conector de servidor de Microsoft SQL pueda conectarse.

Para el conector SQL azure, solo debe especificar el nombre del servidor o la dirección IP a la que desea conectarse. Azure SQL connector solo admite la autenticación de conexión de Azure Active Directory Open ID (OIDC) para conectarse a la base de datos.

Para mayor seguridad, puede configurar reglas de firewall IP para su servidor o base de datos SQL Azure. Para obtener más información sobre cómo configurar reglas de firewall IP, consulte la documentación sobre [las reglas de firewall IP](https://docs.microsoft.com/azure/azure-sql/database/firewall-configure). Agregue los siguientes intervalos IP de cliente en la configuración del firewall.

| Región | Intervalo IP |
| ------------ | ------------ |
| NAM | 52.250.92.252/30, 52.224.250.216/30 |
| EUR | 20.54.41.208/30, 51.105.159.88/30 |
| APC | 52.139.188.212/30, 20.43.146.44/30 |

Para buscar en el contenido de la base de datos, debe especificar SQL al configurar el conector. Estas SQL necesitan nombrar todas las columnas de base de datos que desea indizar (es decir, las propiedades de origen), incluidas las combinaciones de SQL que deben realizarse para obtener todas las columnas. Para restringir el acceso a los resultados de búsqueda, debe especificar listas de control de acceso (ACL) dentro de SQL consultas al configurar el conector.

## <a name="step-3a-full-crawl-required"></a>Paso 3a: Rastreo completo (obligatorio)

En este paso, se configura la consulta SQL que ejecuta un rastreo completo de la base de datos. El rastreo completo selecciona todas las columnas o propiedades donde desea seleccionar las opciones **Query**, **Search** o **Retrieve**. También puede especificar columnas de ACL para restringir el acceso de los resultados de búsqueda a usuarios o grupos específicos.

> [!Tip]
> Para obtener todas las columnas que necesita, puede unir varias tablas.

![Script que muestra OrderTable y AclTable con propiedades de ejemplo](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>Seleccionar columnas de datos (obligatorio) y columnas acl (opcional)

En el ejemplo se muestra una selección de cinco columnas de datos que contienen los datos de la búsqueda: OrderId, OrderTitle, OrderDesc, CreatedDateTime e IsDeleted. Para establecer permisos de vista para cada fila de datos, puede seleccionar opcionalmente estas columnas de ACL: AllowedUsers, AllowedGroups, DeniedUsers y DeniedGroups. Todas estas columnas de datos también tienen las opciones **Query**, **Search** o **Retrieve**.

Seleccione columnas de datos como se muestra en esta consulta de ejemplo: `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`

Para administrar el acceso a los resultados de búsqueda, puede especificar una o más columnas de ACL en la consulta. El SQL permite controlar el acceso por nivel de registro. Puede elegir tener el mismo control de acceso para todos los registros de una tabla. Si la información de acl se almacena en una tabla independiente, es posible que deba hacer una combinación con dichas tablas en la consulta.

A continuación se describe el uso de cada una de las columnas acl de la consulta anterior. En la siguiente lista se explican los cuatro mecanismos **de control de acceso**.

- **AllowedUsers:** esta columna especifica la lista de id. de usuario que pueden tener acceso a los resultados de la búsqueda. En el siguiente ejemplo, lista de usuarios: john@contoso.com, keith@contoso.com y lisa@contoso.com solo tendrían acceso a un registro con OrderId = 12.
- **AllowedGroups:** esta columna especifica el grupo de usuarios que podrán obtener acceso a los resultados de la búsqueda. En el ejemplo siguiente, los grupos sales-team@contoso.com solo tendrían acceso al registro con OrderId = 12.
- **DeniedUsers:** esta columna especifica la lista de usuarios que no **tienen** acceso a los resultados de búsqueda. En el siguiente ejemplo, los usuarios john@contoso.com y keith@contoso.com no tienen acceso al registro con OrderId = 13, mientras que todos los demás tienen acceso a este registro.
- **DeniedGroups:** esta columna especifica el grupo de usuarios que no tienen **acceso** a los resultados de búsqueda. En el siguiente ejemplo, los grupos engg-team@contoso.com y pm-team@contoso.com no tienen acceso al registro con OrderId = 15, mientras que todos los demás tienen acceso a este registro.  

![Datos de ejemplo que muestran OrderTable y AclTable con propiedades de ejemplo](media/MSSQL-ACL1.png)

### <a name="supported-data-types"></a>Tipos de datos admitidos

En la tabla siguiente se resumen los SQL de datos compatibles con los conectores MS SQL y Azure SQL datos. La tabla también resume el tipo de datos de indización para el tipo SQL datos admitido. Para obtener más información sobre los tipos de datos compatibles con conectores de Microsoft Graph para la indización, consulte la documentación sobre tipos [de recursos de propiedad](https://docs.microsoft.com/graph/api/resources/property?view=graph-rest-beta#properties&preserve-view=true).

| Categoría | Tipo de datos de origen | Tipo de datos de indización |
| ------------ | ------------ | ------------ |
| Fecha y hora | date <br> datetime <br> datetime2 <br> smalldatetime | datetime |
| Numérico exacto | bigint <br> entero <br> smallint <br> tinyint | int64 |
| Numérico exacto | bit | boolean |
| Numérico aproximado | float <br> real | double |
| Cadena de caracteres | char <br> varchar <br> text | cadena |
| Cadenas de caracteres Unicode | nchar <br> nvarchar <br> ntext | string |
| Otros tipos de datos | uniqueidentifier | string |

Para cualquier otro tipo de datos actualmente no compatible directamente, la columna debe convertirse explícitamente en un tipo de datos admitido.

### <a name="watermark-required"></a>Marca de agua (obligatorio)

Para evitar sobrecargar la base de datos, el conector por lotes y reanuda las consultas de rastreo completo con una columna de marca de agua de rastreo completo. Al usar el valor de la columna de marca de agua, se captura cada lote posterior y se reanuda la consulta desde el último punto de control. Básicamente, estos mecanismos controlan la actualización de datos para rastreos completos.

Cree fragmentos de código de consulta para marcas de agua como se muestra en estos ejemplos:

- `WHERE (CreatedDateTime > @watermark)`. Cite el nombre de la columna de marca de agua con la palabra clave reservada `@watermark` . Si el criterio de ordenación de la columna de marca de agua es ascendente, use `>` ; de lo contrario, use `<` .
- `ORDER BY CreatedDateTime ASC`. Ordene en la columna de marca de agua en orden ascendente o descendente.

En la configuración que se muestra en la siguiente imagen, `CreatedDateTime` se encuentra la columna de marca de agua seleccionada. Para capturar el primer lote de filas, especifique el tipo de datos de la columna de marca de agua. En este caso, el tipo de datos es `DateTime` .

![Configuración de columna de marca de agua](media/MSSQL-watermark.png)

La primera consulta captura el primer **número N** de filas mediante: "CreatedDateTime > 1 de enero de 1753 00:00:00" (valor mínimo del tipo de datos DateTime). Después de capturar el primer lote, el valor más alto de devuelto en el lote se guarda como punto de control si las filas se ordenan `CreatedDateTime` en orden ascendente. Un ejemplo es el 1 de marzo de 2019 03:00:00. A continuación, se captura el siguiente lote de filas **N** mediante "CreatedDateTime > March 1, 2019 03:00:00" en la consulta.

### <a name="skipping-soft-deleted-rows-optional"></a>Omitir filas eliminadas temporalmente (opcional)

Para excluir las filas eliminadas temporalmente en la base de datos para que no se indexe, especifique el nombre y el valor de la columna de eliminación temporal que indica que la fila se ha eliminado.

![Configuración de eliminación temporal: "Columna de eliminación temporal" y "Valor de la columna de eliminación temporal que indica una fila eliminada"](media/MSSQL-softdelete.png)

### <a name="full-crawl-manage-search-permissions"></a>Rastreo completo: administrar permisos de búsqueda

Seleccione Administrar permisos para elegir las **distintas** columnas de control de acceso (ACL) que especifican el mecanismo de control de acceso. Seleccione el nombre de columna que especificó en la consulta completa SQL rastreo.

Se espera que cada una de las columnas acl sea una columna de varios valores. Estos valores de identificador múltiples se pueden separar mediante separadores como punto y coma (;), coma (,), y así sucesivamente. Debe especificar este separador en el campo **separador de** valores.

Se admiten los siguientes tipos de id. para usar como ACL:

- **Nombre principal de usuario (UPN):** un nombre principal de usuario (UPN) es el nombre de un usuario del sistema en un formato de dirección de correo electrónico. Un UPN (por ejemplo: john.doe@domain.com) consta del nombre de usuario (nombre de inicio de sesión), separador (símbolo @) y nombre de dominio (sufijo UPN).
- **Identificador de Azure Active Directory (AAD):** en Azure AD, cada usuario o grupo tiene un identificador de objeto similar a 'e0d3ad3d-0000-1111-2222-3c5f5c52ab9b'.
- Id. de seguridad de **Active Directory (AD):** en una configuración de AD local, todos los usuarios y grupos tienen un identificador de seguridad único inmutable que tiene un aspecto similar a 'S-1-5-21-3878594291-2115959936-132693609-65242.'

![Configuración de permisos de búsqueda para configurar listas de control de acceso](media/MSSQL-ACL2.png)

## <a name="step-3b-incremental-crawl-optional"></a>Paso 3b: Rastreo incremental (opcional)

En este paso opcional, proporcione una consulta SQL para ejecutar un rastreo incremental de la base de datos. Con esta consulta, el SQL determina los cambios realizados en los datos desde el último rastreo incremental. Al igual que en el rastreo completo, seleccione todas las columnas en las que desee seleccionar las opciones **Consulta,** **Búsqueda** o **Recuperar**. Especifique el mismo conjunto de columnas acl que especificó en la consulta de rastreo completa.

Los componentes de la siguiente imagen son similares a los componentes de rastreo completos con una excepción. En este caso, "ModifiedDateTime" es la columna de marca de agua seleccionada. Revise los [pasos de rastreo completos](#step-3a-full-crawl-required) para obtener información sobre cómo escribir la consulta de rastreo incremental y vea la siguiente imagen como un ejemplo.

![Script de rastreo incremental que muestra las propiedades OrderTable, AclTable y example que se pueden usar.](media/MSSQL-incrcrawl.png)

## <a name="step-4-assign-property-labels"></a>Paso 4: Asignar etiquetas de propiedades

Siga las instrucciones [generales de configuración](https://docs.microsoft.com/microsoftsearch/configure-connector).

<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-5-manage-schema"></a>Paso 5: Administrar esquema

Siga las instrucciones [generales de configuración](https://docs.microsoft.com/microsoftsearch/configure-connector).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-6-manage-search-permissions"></a>Paso 6: Administrar permisos de búsqueda

Puede elegir usar las [ACL](#full-crawl-manage-search-permissions) especificadas en la pantalla de rastreo completa o puede invalidarlas para que el contenido sea visible para todos.

## <a name="step-7-choose-refresh-settings"></a>Paso 7: Elegir la configuración de actualización

Siga las instrucciones [generales de configuración](https://docs.microsoft.com/microsoftsearch/configure-connector).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-8-review-connection"></a>Paso 8: Revisar la conexión

Siga las instrucciones [generales de configuración](https://docs.microsoft.com/microsoftsearch/configure-connector).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Next steps: Customize the search results page

Create your own verticals and result types, so end users can view search results from new connections. Without this step, data from your connection won't show up on the search results page.

To learn more about how to create your verticals and MRTs, see [Search results page customization](customize-search-page.md).-->

<!---## Troubleshooting-->

<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a>Limitaciones

Los SQL tienen estas limitaciones en la versión preliminar:

- Conector SQL servidor de Microsoft: la base de datos local debe ejecutarse SQL versión de servidor 2008 o posterior.
- La suscripción a M365 y la suscripción de Azure (que hospeda la base de datos SQL Azure) deben estar dentro del mismo Azure Active Directory.
- Las ACL solo se admiten mediante un nombre principal de usuario (UPN), Azure Active Directory (Azure AD) o Seguridad de Active Directory.
- No se admite la indización de contenido enriquecido dentro de las columnas de base de datos. Ejemplos de este contenido son HTML, JSON, XML, blobs y análisis de documentos que existen como vínculos dentro de las columnas de la base de datos.
