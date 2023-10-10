# NeoRed.Api.CampaignsApi

Todas las URL son relativas a

| Método | Solicitud HTTP | Descripción |
|--------|--------------|-------------|
| [**CampaignsByNameDelete**](CampaignsApi.md#campaignsbynamedelete) | **ELIMINAR** /campañas/{nombre} | Eliminar campaña |
| [**CampaignsByNameGet**](CampaignsApi.md#campaignsbynameget) | **OBTENER** /campañas/{nombre} | Cargar campaña |
| [**CampaignsByNamePut**](CampaignsApi.md#campaignsbynameput) | **PUT** /campañas/{nombre} | Campaña de actualización |
| [**CampaignsGet**](CampaignsApi.md#campaignsget) | **OBTENER** /campañas | Cargar campañas |
| [**CampaignsPost**](CampaignsApi.md#campaignspost) | **POST** /campañas | Agregar campaña |

<a name="campaignsbynamedelete"></a>
# **CampañasPorNombreEliminar**
> void CampaignsByNameDelete (nombre de cadena)

Eliminar campaña

Eliminar la campaña específica. Esto no cancela el correo electrónico en curso; consulte Cancelación en curso. Nivel de acceso requerido: Modificar campañas

### Ejemplo
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using ElasticEmail.Api;
using ElasticEmail.Client;
using ElasticEmail.Model;

namespace Example
{
    public class CampaignsByNameDeleteExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.elasticemail.com/v4";
            // Configure API key authorization: apikey
            config.AddApiKey("X-ElasticEmail-ApiKey", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("X-ElasticEmail-ApiKey", "Bearer");

            var apiInstance = new CampaignsApi(config);
            var name = "name_example";  // string | Name of Campaign to delete

            try
            {
                // Delete Campaign
                apiInstance.CampaignsByNameDelete(name);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CampaignsApi.CampaignsByNameDelete: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Uso de la variante CampaignsByNameDeleteWithHttpInfo
Esto devuelve un objeto ApiResponse que contiene los datos de respuesta, el código de estado y los encabezados.

```csharp
try
{
    // Delete Campaign
    apiInstance.CampaignsByNameDeleteWithHttpInfo(name);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CampaignsApi.CampaignsByNameDeleteWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parámetros

| Nombre | Tipo | Descripción | Notas |
|------|------|-------------|-------|
| **nombre** | **cadena** | Nombre de la campaña a eliminar | |

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

<a name="campaignsbynameget"></a>
# **CampañasPorNombreObtener**
> Campaña CampaignsByNameGet (nombre de cadena)

Cargar campaña

Devuelve los detalles de la campaña especificada. Nivel de acceso requerido: Ver campañas

### Ejemplo
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using ElasticEmail.Api;
using ElasticEmail.Client;
using ElasticEmail.Model;

namespace Example
{
    public class CampaignsByNameGetExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.elasticemail.com/v4";
            // Configure API key authorization: apikey
            config.AddApiKey("X-ElasticEmail-ApiKey", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("X-ElasticEmail-ApiKey", "Bearer");

            var apiInstance = new CampaignsApi(config);
            var name = "name_example";  // string | Name of Campaign to get

            try
            {
                // Load Campaign
                Campaign result = apiInstance.CampaignsByNameGet(name);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CampaignsApi.CampaignsByNameGet: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Uso de la variante CampaignsByNameGetWithHttpInfo
Esto devuelve un objeto ApiResponse que contiene los datos de respuesta, el código de estado y los encabezados.

```csharp
try
{
    // Load Campaign
    ApiResponse<Campaign> response = apiInstance.CampaignsByNameGetWithHttpInfo(name);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CampaignsApi.CampaignsByNameGetWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parámetros

| Nombre | Tipo | Descripción | Notas |
|------|------|-------------|-------|
| **nombre** | **cadena** | Nombre de la campaña a conseguir | |

### Tipo de devolución

[**Campaña**](Campaña.md)

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

<a name="campaignsbynameput"></a>
# **CampañasPorNombrePut**
> Campaña CampaignsByNamePut (nombre de cadena, campaña de campaña)

Campaña de actualización

Actualiza una campaña agregada anteriormente. Sólo se pueden actualizar las campañas activas y en pausa. Nivel de acceso requerido: Modificar campañas

### Ejemplo
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using ElasticEmail.Api;
using ElasticEmail.Client;
using ElasticEmail.Model;

namespace Example
{
    public class CampaignsByNamePutExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.elasticemail.com/v4";
            // Configure API key authorization: apikey
            config.AddApiKey("X-ElasticEmail-ApiKey", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("X-ElasticEmail-ApiKey", "Bearer");

            var apiInstance = new CampaignsApi(config);
            var name = "name_example";  // string | Name of Campaign to update
            var campaign = new Campaign(); // Campaign | JSON representation of a campaign

            try
            {
                // Update Campaign
                Campaign result = apiInstance.CampaignsByNamePut(name, campaign);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CampaignsApi.CampaignsByNamePut: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Uso de la variante CampaignsByNamePutWithHttpInfo
Esto devuelve un objeto ApiResponse que contiene los datos de respuesta, el código de estado y los encabezados.

```csharp
try
{
    // Update Campaign
    ApiResponse<Campaign> response = apiInstance.CampaignsByNamePutWithHttpInfo(name, campaign);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CampaignsApi.CampaignsByNamePutWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parámetros

| Nombre | Tipo | Descripción | Notas |
|------|------|-------------|-------|
| **nombre** | **cadena** | Nombre de la campaña a actualizar | |
| **campaña** | [**Campaña**](Campaña.md) | Representación JSON de una campaña | |

### Tipo de devolución

[**Campaña**](Campaña.md)

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

<a name="campaignsget"></a>
# **CampañasObtener**
> Listar&lt;Campaña&gt; CampaignsGet (búsqueda de cadena = nulo, int? offset = nulo, int? límite = nulo)

Cargar campañas

Devuelve una lista de todas sus campañas. Limitado a 1000 resultados. Nivel de acceso requerido: Ver campañas

### Ejemplo
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using ElasticEmail.Api;
using ElasticEmail.Client;
using ElasticEmail.Model;

namespace Example
{
    public class CampaignsGetExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.elasticemail.com/v4";
            // Configure API key authorization: apikey
            config.AddApiKey("X-ElasticEmail-ApiKey", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("X-ElasticEmail-ApiKey", "Bearer");

            var apiInstance = new CampaignsApi(config);
            var search = "search_example";  // string | Text fragment used for searching in Campaign name (using the 'contains' rule) (optional) 
            var offset = 20;  // int? | How many items should be returned ahead. (optional) 
            var limit = 100;  // int? | Maximum number of returned items. (optional) 

            try
            {
                // Load Campaigns
                List<Campaign> result = apiInstance.CampaignsGet(search, offset, limit);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CampaignsApi.CampaignsGet: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Uso de la variante CampaignsGetWithHttpInfo
Esto devuelve un objeto ApiResponse que contiene los datos de respuesta, el código de estado y los encabezados.

```csharp
try
{
    // Load Campaigns
    ApiResponse<List<Campaign>> response = apiInstance.CampaignsGetWithHttpInfo(search, offset, limit);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CampaignsApi.CampaignsGetWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parámetros

| Nombre | Tipo | Descripción | Notas |
|------|------|-------------|-------|
| **buscar** | **cadena** | Fragmento de texto utilizado para buscar en el nombre de la campaña (usando la regla "contiene") | [opcional] |
| **compensación** | **int?** | ¿Cuántos artículos se deben devolver con anticipación? | [opcional] |
| **límite** | **int?** | Número máximo de artículos devueltos. | [opcional] |

### Tipo de devolución

[**Lista&lt;Campaña&gt;**](Campaña.md)

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

<a name="publicación de campaña"></a>
# **Publicación de campañas**
> Campaña CampañasPost (Campaña campaña)

Agregar campaña

Agregue una campaña para su procesamiento. Nivel de acceso requerido: Modificar campañas

### Ejemplo
```csharp
using System.Collections.Generic;
using System.Diagnostics;
using ElasticEmail.Api;
using ElasticEmail.Client;
using ElasticEmail.Model;

namespace Example
{
    public class CampaignsPostExample
    {
        public static void Main()
        {
            Configuration config = new Configuration();
            config.BasePath = "https://api.elasticemail.com/v4";
            // Configure API key authorization: apikey
            config.AddApiKey("X-ElasticEmail-ApiKey", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // config.AddApiKeyPrefix("X-ElasticEmail-ApiKey", "Bearer");

            var apiInstance = new CampaignsApi(config);
            var campaign = new Campaign(); // Campaign | JSON representation of a campaign

            try
            {
                // Add Campaign
                Campaign result = apiInstance.CampaignsPost(campaign);
                Debug.WriteLine(result);
            }
            catch (ApiException  e)
            {
                Debug.Print("Exception when calling CampaignsApi.CampaignsPost: " + e.Message);
                Debug.Print("Status Code: " + e.ErrorCode);
                Debug.Print(e.StackTrace);
            }
        }
    }
}
```

#### Uso de la variante CampaignsPostWithHttpInfo
Esto devuelve un objeto ApiResponse que contiene los datos de respuesta, el código de estado y los encabezados.

```csharp
try
{
    // Add Campaign
    ApiResponse<Campaign> response = apiInstance.CampaignsPostWithHttpInfo(campaign);
    Debug.Write("Status Code: " + response.StatusCode);
    Debug.Write("Response Headers: " + response.Headers);
    Debug.Write("Response Body: " + response.Data);
}
catch (ApiException e)
{
    Debug.Print("Exception when calling CampaignsApi.CampaignsPostWithHttpInfo: " + e.Message);
    Debug.Print("Status Code: " + e.ErrorCode);
    Debug.Print(e.StackTrace);
}
```

### Parámetros

| Nombre | Tipo | Descripción | Notas |
|------|------|-------------|-------|
| **campaña** | [**Campaña**](Campaña.md) | Representación JSON de una campaña | |

### Tipo de devolución

[**Campaña**](Campaña.md)

### Autorización

[apikey](../README.md#apikey)

### encabezados de solicitud HTTP

  - **Tipo de contenido**: aplicación/json
  - **Aceptar**: aplicación/json


### Detalles de la respuesta HTTP
| Código de estado | Descripción | Encabezados de respuesta |
|-------------|-------------|------------------|
| **201** | Creado | - |

[[Volver al inicio]](#) [[Volver a la lista de API]](../README.md#documentation-for-api-endpoints) [[Volver a la lista de modelos]](../README.md# documentación-para-modelos) [[Volver a README]](../README.md)
