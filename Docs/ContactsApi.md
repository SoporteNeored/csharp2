# ElasticEmail.Api.ContactosApi

Todos los URI son relativos 

| Método | Solicitud HTTP | Descripción |
|--------|--------------|-------------|
| [**ContactosByEmailDelete**](ContactsApi.md#contactsbyemaildelete) | **ELIMINAR** /contactos/{correo electrónico} | Eliminar contacto |
| [**ContactosByEmailGet**](ContactosApi.md#contactsbyemailget) | **OBTENER** /contactos/{correo electrónico} | Cargar Contacto |
| [**ContactosByEmailPut**](ContactosApi.md#contactsbyemailput) | **PONER** /contactos/{correo electrónico} | Actualizar contacto |
| [**ContactsDeletePost**](ContactsApi.md#contactsdeletepost) | **POST** /contactos/eliminar | Eliminar contactos de forma masiva |
| [**ContactsExportByIdStatusGet**](ContactsApi.md#contactsexportbyidstatusget) | **OBTENER** /contactos/exportar/{id}/status | Verificar estado de exportación |
| [**ContactsExportPost**](ContactsApi.md#contactsexportpost) | **POST** /contactos/exportar | Exportar contactos |
| [**ContactosGet**](ContactosApi.md#contactsget) | **OBTENER** /contactos | Cargar contactos |
| [**ContactsImportPost**](ContactsApi.md#contactsimportpost) | **POST** /contactos/importar | Cargar contactos |
| [**Publicación de contactos**](ContactsApi.md#publicar-contactos) | **POST** /contactos | Agregar contacto |

<a name="contactsbyemaildelete"></a>
# **ContactosPorEmailEliminar**
> anular ContactsByEmailDelete (cadena de correo electrónico)

Borrar contacto

Elimina el contacto proporcionado. Nivel de acceso requerido: Modificar contactos

### Ejemplo
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using ElasticEmail.Api;
using ElasticEmail.Client;
using ElasticEmail.Model;

namespace Example
{
    public class ContactsByEmailDeleteExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.elasticemail.com/v4";
            // Configure API key authorization: apikey
            config.AddApiKey("X-ElasticEmail-ApiKey", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("X-ElasticEmail-ApiKey", "Bearer");

            var apiInstance = new ContactsApi(config);
            var email = mail@example.com;  // string | Proper email address.

            try
            {
                // Delete Contact
                apiInstance.ContactsByEmailDelete(email);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ContactsApi.ContactsByEmailDelete: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Uso de la variante ContactsByEmailDeleteWithHttpInfo
Esto devuelve un objeto ApiResponse que contiene los datos de respuesta, el código de estado y los encabezados.

```csharp
try
{
    // Delete Contact
    apiInstance.ContactsByEmailDeleteWithHttpInfo(email);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ContactsApi.ContactsByEmailDeleteWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parámetros

| Nombre | Tipo | Descripción | Notas |
|------|------|-------------|-------|
| **correo electrónico** | **cadena** | Dirección de correo electrónico adecuada. | |

### Tipo de devolución

void (cuerpo de respuesta vacío)

### Autorización

[apikey](../README.md#apikey)

### encabezados de solicitud HTTP

  - **Tipo de contenido**: No definido
  - **Aceptar**: No definido

### Detalles de la respuesta HTTP
| Código de estado | Descripción | Encabezados de respuesta |
|-------------|-------------|------------------|
| **200** | Aceptar | - |

[[Volver al inicio]](#) [[Volver a la lista de API]](../README.md#documentation-for-api-endpoints) [[Volver a la lista de modelos]](../README.md# documentación-para-modelos) [[Volver a README]](../README.md)

<a name="contactsbyemailget"></a>
# **ContactosPorEmailGet**
> Contacto ContactsByEmailGet (cadena de correo electrónico)

Cargar contacto

Cargue información de contacto detallada para el correo electrónico especificado. Nivel de acceso requerido: Ver contactos

### Ejemplo
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using ElasticEmail.Api;
using ElasticEmail.Client;
using ElasticEmail.Model;

namespace Example
{
    public class ContactsByEmailGetExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.elasticemail.com/v4";
            // Configure API key authorization: apikey
            config.AddApiKey("X-ElasticEmail-ApiKey", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("X-ElasticEmail-ApiKey", "Bearer");

            var apiInstance = new ContactsApi(config);
            var email = mail@example.com;  // string | Proper email address.

            try
            {
                // Load Contact
                Contact result = apiInstance.ContactsByEmailGet(email);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ContactsApi.ContactsByEmailGet: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Uso de la variante ContactsByEmailGetWithHttpInfo
Esto devuelve un objeto ApiResponse que contiene los datos de respuesta, el código de estado y los encabezados.

```csharp
try
{
    // Load Contact
    ApiResponse<Contact> response = apiInstance.ContactsByEmailGetWithHttpInfo(email);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ContactsApi.ContactsByEmailGetWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parámetros

| Nombre | Tipo | Descripción | Notas |
|------|------|-------------|-------|
| **correo electrónico** | **cadena** | Dirección de correo electrónico adecuada. | |

### Tipo de devolución

[**Contacto**](Contact.md)

### Autorización

[apikey](../README.md#apikey)

### encabezados de solicitud HTTP

  - **Tipo de contenido**: No definido
  - **Aceptar**: aplicación/json


### Detalles de la respuesta HTTP
| Código de estado | Descripción | Encabezados de respuesta |
|-------------|-------------|------------------|
| **200** | Aceptar | - |

[[Volver al inicio]](#) [[Volver a la lista de API]](../README.md#documentation-for-api-endpoints) [[Volver a la lista de modelos]](../README.md# documentación-para-modelos) [[Volver a README]](../README.md)

<a name="contactsbyemailput"></a>
# **ContactosPorEmailPut**
> Contacto ContactsByEmailPut (cadena de correo electrónico, ContactUpdatePayload contactUpdatePayload)

Actualizar contacto

Actualizar contacto seleccionado. Los campos del contacto omitidos no se cambiarán. Nivel de acceso requerido: Modificar contactos

### Ejemplo
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using ElasticEmail.Api;
using ElasticEmail.Client;
using ElasticEmail.Model;

namespace Example
{
    public class ContactsByEmailPutExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.elasticemail.com/v4";
            // Configure API key authorization: apikey
            config.AddApiKey("X-ElasticEmail-ApiKey", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("X-ElasticEmail-ApiKey", "Bearer");

            var apiInstance = new ContactsApi(config);
            var email = mail@example.com;  // string | Proper email address.
            var contactUpdatePayload = new ContactUpdatePayload(); // ContactUpdatePayload | 

            try
            {
                // Update Contact
                Contact result = apiInstance.ContactsByEmailPut(email, contactUpdatePayload);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ContactsApi.ContactsByEmailPut: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Uso de la variante ContactsByEmailPutWithHttpInfo
Esto devuelve un objeto ApiResponse que contiene los datos de respuesta, el código de estado y los encabezados.

```csharp
try
{
    // Update Contact
    ApiResponse<Contact> response = apiInstance.ContactsByEmailPutWithHttpInfo(email, contactUpdatePayload);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ContactsApi.ContactsByEmailPutWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parámetros

| Nombre | Tipo | Descripción | Notas |
|------|------|-------------|-------|
| **correo electrónico** | **cadena** | Dirección de correo electrónico adecuada. | |
| **contactUpdatePayload** | [**ContactUpdatePayload**](ContactUpdatePayload.md) | | |

### Tipo de devolución

[**Contacto**](Contact.md)

### Autorización

[apikey](../README.md#apikey)

### encabezados de solicitud HTTP

  - **Tipo de contenido**: aplicación/json
  - **Aceptar**: aplicación/json


### Detalles de la respuesta HTTP
| Código de estado | Descripción | Encabezados de respuesta |
|-------------|-------------|------------------|
| **200** | Aceptar | - |

[[Volver al inicio]](#) [[Volver a la lista de API]](../README.md#documentation-for-api-endpoints) [[Volver a la lista de modelos]](../README.md# documentación-para-modelos) [[Volver a README]](../README.md)

<a name="contactsdeletepost"></a>
# **ContactosEliminar publicación**
> anular ContactosDeletePost (EmailsPayload emailsPayload)

Eliminar contactos en masa

Elimina los contactos proporcionados de forma masiva. Nivel de acceso requerido: Modificar contactos

### Ejemplo
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using ElasticEmail.Api;
using ElasticEmail.Client;
using ElasticEmail.Model;

namespace Example
{
    public class ContactsDeletePostExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.elasticemail.com/v4";
            // Configure API key authorization: apikey
            config.AddApiKey("X-ElasticEmail-ApiKey", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("X-ElasticEmail-ApiKey", "Bearer");

            var apiInstance = new ContactsApi(config);
            var emailsPayload = new EmailsPayload(); // EmailsPayload | Provide either rule or a list of emails, not both.

            try
            {
                // Delete Contacts Bulk
                apiInstance.ContactsDeletePost(emailsPayload);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ContactsApi.ContactsDeletePost: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Usando la variante ContactsDeletePostWithHttpInfo
Esto devuelve un objeto ApiResponse que contiene los datos de respuesta, el código de estado y los encabezados.

```csharp
try
{
    // Delete Contacts Bulk
    apiInstance.ContactsDeletePostWithHttpInfo(emailsPayload);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ContactsApi.ContactsDeletePostWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parámetros

| Nombre | Tipo | Descripción | Notas |
|------|------|-------------|-------|
| **carga útil de correos electrónicos** | [**Carga útil de correos electrónicos**](Carga útil de correos electrónicos.md) | Proporcione una regla o una lista de correos electrónicos, no ambas. | |

### Tipo de devolución

void (cuerpo de respuesta vacío)

### Autorización

[apikey](../README.md#apikey)

### encabezados de solicitud HTTP

  - **Tipo de contenido**: aplicación/json
  - **Aceptar**: No definido


### Detalles de la respuesta HTTP
| Código de estado | Descripción | Encabezados de respuesta |
|-------------|-------------|------------------|
| **200** | Aceptar | - |

[[Volver al inicio]](#) [[Volver a la lista de API]](../README.md#documentation-for-api-endpoints) [[Volver a la lista de modelos]](../README.md# documentación-para-modelos) [[Volver a README]](../README.md)

<a name="contactsexportbyidstatusget"></a>
# **ContactosExportarByIdStatusGet**
> ExportStatus ContactsExportByIdStatusGet (identificador de cadena)

Verificar estado de exportación

Consulta el estado actual de la exportación. Nivel de acceso requerido: Exportar
### Ejemplo
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using ElasticEmail.Api;
using ElasticEmail.Client;
using ElasticEmail.Model;

namespace Example
{
    public class ContactsExportByIdStatusGetExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.elasticemail.com/v4";
            // Configure API key authorization: apikey
            config.AddApiKey("X-ElasticEmail-ApiKey", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("X-ElasticEmail-ApiKey", "Bearer");

            var apiInstance = new ContactsApi(config);
            var id = E33EBA7A-C20D-4D3D-8F2F-5EEF42F58E6F;  // string | ID of the exported file

            try
            {
                // Check Export Status
                ExportStatus result = apiInstance.ContactsExportByIdStatusGet(id);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ContactsApi.ContactsExportByIdStatusGet: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Uso de la variante ContactsExportByIdStatusGetWithHttpInfo
Esto devuelve un objeto ApiResponse que contiene los datos de respuesta, el código de estado y los encabezados.

```csharp
try
{
    // Check Export Status
    ApiResponse<ExportStatus> response = apiInstance.ContactsExportByIdStatusGetWithHttpInfo(id);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ContactsApi.ContactsExportByIdStatusGetWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parámetros

| Nombre | Tipo | Descripción | Notas |
|------|------|-------------|-------|
| **identificación** | **cadena** | ID del archivo exportado | |

### Tipo de devolución

[**Estado de exportación**](Estado de exportación.md)

### Autorización

[apikey](../README.md#apikey)

### encabezados de solicitud HTTP

  - **Tipo de contenido**: No definido
  - **Aceptar**: aplicación/json


### Detalles de la respuesta HTTP
| Código de estado | Descripción | Encabezados de respuesta |
|-------------|-------------|------------------|
| **200** | Aceptar | - |

[[Volver al inicio]](#) [[Volver a la lista de API]](../README.md#documentation-for-api-endpoints) [[Volver a la lista de modelos]](../README.md# documentación-para-modelos) [[Volver a README]](../README.md)

<a name="contactsexportpost"></a>
# **ContactosExportarPublicar**
> ExportLink ContactsExportPost (ExportFileFormats? fileFormat = nulo, regla de cadena = nulo, Lista<cadena> correos electrónicos = nulo, CompresiónFormat? compresiónFormat = nulo, cadena nombre de archivo = nulo)

Exportar contactos

Solicite una exportación de contactos específicos. Nivel de acceso requerido: Exportar

### Ejemplo
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using ElasticEmail.Api;
using ElasticEmail.Client;
using ElasticEmail.Model;

namespace Example
{
    public class ContactsExportPostExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.elasticemail.com/v4";
            // Configure API key authorization: apikey
            config.AddApiKey("X-ElasticEmail-ApiKey", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("X-ElasticEmail-ApiKey", "Bearer");

            var apiInstance = new ContactsApi(config);
            var fileFormat = (ExportFileFormats) "Csv";  // ExportFileFormats? | Format of the exported file (optional) 
            var rule = Status%20=%20Engaged;  // string | Query used for filtering. (optional) 
            var emails = new List<string>(); // List<string> | Comma delimited list of contact emails (optional) 
            var compressionFormat = (CompressionFormat) "None";  // CompressionFormat? | FileResponse compression format. None or Zip. (optional) 
            var fileName = filename.txt;  // string | Name of your file including extension. (optional) 

            try
            {
                // Export Contacts
                ExportLink result = apiInstance.ContactsExportPost(fileFormat, rule, emails, compressionFormat, fileName);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ContactsApi.ContactsExportPost: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Usando la variante ContactsExportPostWithHttpInfo
Esto devuelve un objeto ApiResponse que contiene los datos de respuesta, el código de estado y los encabezados.

```csharp
try
{
    // Export Contacts
    ApiResponse<ExportLink> response = apiInstance.ContactsExportPostWithHttpInfo(fileFormat, rule, emails, compressionFormat, fileName);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ContactsApi.ContactsExportPostWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parámetros

| Nombre | Tipo | Descripción | Notas |
|------|------|-------------|-------|
| **formato de archivo** | **¿Exportar formatos de archivo?** | Formato del archivo exportado | [opcional] |
| **regla** | **cadena** | Consulta utilizada para el filtrado. | [opcional] |
| **correos electrónicos** | [**Lista&lt;cadena&gt;**](cadena.md) | Lista delimitada por comas de correos electrónicos de contacto | [opcional] |
| **formato de compresión** | **¿Formato de compresión?** | Formato de compresión FileResponse. Ninguno o Zip. | [opcional] |
| **nombre de archivo** | **cadena** | Nombre de su archivo, incluida la extensión. | [opcional] |

### Tipo de devolución

[**ExportarEnlace**](ExportarEnlace.md)

### Autorización

[apikey](../README.md#apikey)

### encabezados de solicitud HTTP

  - **Tipo de contenido**: No definido
  - **Aceptar**: aplicación/json


### Detalles de la respuesta HTTP
| Código de estado | Descripción | Encabezados de respuesta |
|-------------|-------------|------------------|
| **202** | Aceptado | - |

[[Volver al inicio]](#) [[Volver a la lista de API]](../README.md#documentation-for-api-endpoints) [[Volver a la lista de modelos]](../README.md# documentación-para-modelos) [[Volver a README]](../README.md)

<a nombre="contactosget"></a>
# **ContactosObtener**
> Lista&lt;Contacto&gt; ContactosGet (int? límite = nulo, int? desplazamiento = nulo)

Cargar contactos

Devuelve una lista de contactos. Nivel de acceso requerido: Ver contactos

### Ejemplo
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using ElasticEmail.Api;
using ElasticEmail.Client;
using ElasticEmail.Model;

namespace Example
{
    public class ContactsGetExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.elasticemail.com/v4";
            // Configure API key authorization: apikey
            config.AddApiKey("X-ElasticEmail-ApiKey", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("X-ElasticEmail-ApiKey", "Bearer");

            var apiInstance = new ContactsApi(config);
            var limit = 100;  // int? | Maximum number of returned items. (optional) 
            var offset = 20;  // int? | How many items should be returned ahead. (optional) 

            try
            {
                // Load Contacts
                List<Contact> result = apiInstance.ContactsGet(limit, offset);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ContactsApi.ContactsGet: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Usando la variante ContactsGetWithHttpInfo
Esto devuelve un objeto ApiResponse que contiene los datos de respuesta, el código de estado y los encabezados.

```csharp
try
{
    // Load Contacts
    ApiResponse<List<Contact>> response = apiInstance.ContactsGetWithHttpInfo(limit, offset);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ContactsApi.ContactsGetWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parámetros

| Nombre | Tipo | Descripción | Notas |
|------|------|-------------|-------|
| **límite** | **int?** | Número máximo de artículos devueltos. | [opcional] |
| **compensación** | **int?** | ¿Cuántos artículos se deben devolver con anticipación? | [opcional] |

### Tipo de devolución

[**Lista&lt;Contacto&gt;**](Contact.md)

### Autorización

[apikey](../README.md#apikey)

### encabezados de solicitud HTTP

  - **Tipo de contenido**: No definido
  - **Aceptar**: aplicación/json


### Detalles de la respuesta HTTP
| Código de estado | Descripción | Encabezados de respuesta |
|-------------|-------------|------------------|
| **200** | Aceptar | - |

[[Volver al inicio]](#) [[Volver a la lista de API]](../README.md#documentation-for-api-endpoints) [[Volver a la lista de modelos]](../README.md# documentación-para-modelos) [[Volver a README]](../README.md)

<a name="contactsimportpost"></a>
# **Publicación de importación de contactos**
> void ContactsImportPost (cadena listName = nulo, cadena encodingName = nulo, cadena fileUrl = nulo, archivo System.IO.Stream = nulo)

Cargar contactos

Cargar contactos desde un archivo. Nivel de acceso requerido: Modificar contactos

### Ejemplo
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using ElasticEmail.Api;
using ElasticEmail.Client;
using ElasticEmail.Model;

namespace Example
{
    public class ContactsImportPostExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.elasticemail.com/v4";
            // Configure API key authorization: apikey
            config.AddApiKey("X-ElasticEmail-ApiKey", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("X-ElasticEmail-ApiKey", "Bearer");

            var apiInstance = new ContactsApi(config);
            var listName = "listName_example";  // string | Name of an existing list to add these contacts to (optional) 
            var encodingName = "encodingName_example";  // string | In what encoding the file is uploaded (optional) 
            var fileUrl = "fileUrl_example";  // string | Optional url of csv to import (optional) 
            var file = new System.IO.MemoryStream(System.IO.File.ReadAllBytes("/path/to/file.txt"));  // System.IO.Stream |  (optional) 

            try
            {
                // Upload Contacts
                apiInstance.ContactsImportPost(listName, encodingName, fileUrl, file);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ContactsApi.ContactsImportPost: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Usando la variante ContactsImportPostWithHttpInfo
Esto devuelve un objeto ApiResponse que contiene los datos de respuesta, el código de estado y los encabezados.

```csharp
try
{
    // Upload Contacts
    apiInstance.ContactsImportPostWithHttpInfo(listName, encodingName, fileUrl, file);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ContactsApi.ContactsImportPostWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parámetros

| Nombre | Tipo | Descripción | Notas |
|------|------|-------------|-------|
| **nombre de lista** | **cadena** | Nombre de una lista existente a la que agregar estos contactos | [opcional] |
| **nombrecodificación** | **cadena** | ¿En qué codificación se carga el archivo? [opcional] |
| **URL de archivo** | **cadena** | URL opcional de csv para importar | [opcional] |
| **archivo** | **Sistema.IO.Stream****Sistema.IO.Stream** | | [opcional] |

### Tipo de devolución

void (cuerpo de respuesta vacío)

### Autorización

[apikey](../README.md#apikey)

### encabezados de solicitud HTTP

  - **Tipo de contenido**: multiparte/datos de formulario
  - **Aceptar**: No definido


### Detalles de la respuesta HTTP
| Código de estado | Descripción | Encabezados de respuesta |
|-------------|-------------|------------------|
| **202** | Aceptado | - |

[[Volver al inicio]](#) [[Volver a la lista de API]](../README.md#documentation-for-api-endpoints) [[Volver a la lista de modelos]](../README.md# documentación-para-modelos) [[Volver a README]](../README.md)

<a name="contactspost"></a>
# **Publicar contactos**
> Lista&lt;Contacto&gt; ContactsPost (List<ContactPayload> contactPayload, List<string> nombres de lista = null)

Agregar contacto

Agregue nuevos contactos a sus listas. Se pueden agregar hasta 1000 (para obtener más información, consulte la solicitud de importación). Nivel de acceso requerido: Modificar contactos

### Ejemplo
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using ElasticEmail.Api;
using ElasticEmail.Client;
using ElasticEmail.Model;

namespace Example
{
    public class ContactsPostExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.elasticemail.com/v4";
            // Configure API key authorization: apikey
            config.AddApiKey("X-ElasticEmail-ApiKey", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("X-ElasticEmail-ApiKey", "Bearer");

            var apiInstance = new ContactsApi(config);
            var contactPayload = new List<ContactPayload>(); // List<ContactPayload> | 
            var listnames = new List<string>(); // List<string> | Names of lists to which the uploaded contacts should be added to (optional) 

            try
            {
                // Add Contact
                List<Contact> result = apiInstance.ContactsPost(contactPayload, listnames);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling ContactsApi.ContactsPost: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Usando la variante ContactsPostWithHttpInfo
Esto devuelve un objeto ApiResponse que contiene los datos de respuesta, el código de estado y los encabezados.

```csharp
try
{
    // Add Contact
    ApiResponse<List<Contact>> response = apiInstance.ContactsPostWithHttpInfo(contactPayload, listnames);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling ContactsApi.ContactsPostWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parámetros

| Nombre | Tipo | Descripción | Notas |
|------|------|-------------|-------|
| **carga útil de contacto** | [**Lista&lt;ContactPayload&gt;**](ContactPayload.md) | | |
| **nombres de lista** | [**Lista&lt;cadena&gt;**](cadena.md) | Nombres de listas a las que se deben agregar los contactos cargados | [opcional] |

### Tipo de devolución

[**Lista&lt;Contacto&gt;**](Contact.md)

### Autorización

[apikey](../README.md#apikey)

### encabezados de solicitud HTTP

  - **Tipo de contenido**: aplicación/json
  - **Aceptar**: aplicación/json


### Detalles de la respuesta HTTP
| Código de estado | Descripción | Encabezados de respuesta |
|-------------|-------------|------------------|
| **200** | Aceptar | - |

[[Volver al inicio]](#) [[Volver a la lista de API]](../README.md#documentation-for-api-endpoints) [[Volver a la lista de modelos]](../README.md# documentación-para-modelos) [[Volver a README]](../README.md)
