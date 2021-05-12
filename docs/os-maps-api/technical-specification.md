---
id: technical-specification
title: Technical specification
description: Technical details for the OS Maps API
hide_table_of_contents: true
slug: /os-maps-api/technical-specification
---

# OS Features API: Technical specification

PLACEHODLER

This guide explains the content of the OS Vector Tile API, and the methods that you can use to call it. Using OS Vector Tile API requires basic knowledge of interacting with web-based products and the application of code libraries such as Mapbox GL JS, Leaflet and ArcGIS API for JavaScript.

OS Vector Tile API is currently available as EPSG:27700 \(British National Grid which is applicable just for GB\) and EPSG:3857 \(Web Mercator which is a global coordinate system\). The maps are available as raw information presented using compressed packets of geographic data using the Protocolbuffer Binary Format \(.pbf\). This provides users optimised maps which render quickly on the web and offer a slick mapping experience.

The API is available using a version of RESTful design with KVP \(Key Value Pair\) elements.

The Vector Tile Service combines the benefits of pre-rendered raster map tiles with vector map data. Compared to an un-tiled vector map, there is a significantly reduced data transfer size, because only data within the current viewport, and at the current zoom level will be transferred.

This data can be accessed, styled and interrogated through a web-based application which is accessible via a browser.

### Technical Detail

OS Vector Tile API requests are structured using RESTful design combined with keyword-value pair \(KVP\) parameter encoding and HTTP GET. All requests must be encoded correctly according to standard [percent-encoding](https://www.w3schools.com/tags/ref_urlencode.asp) procedures for a URI.

Authentication

To use this API you need to authenticate your requests. Before you can authenticate your request you need to add the API into an API Project, which will give you access to a Project API Key and Project API Secret. See the [getting started guide](https://osdatahub.os.uk/docs/vts/gettingStarted) for more information on setting up your API Project.

There are three options for authenticating your API requests:

- **HTTP Header:** You can choose to authenticate your API request using a HTTP header. The header name should be 'key', and the value should be the Project API Key.


- **HTTP Query Parameter:** You can choose to authenticate your API request using a HTTP query parameter. The parameter name should be 'key', and the value should be the Project API Key.


- **OAuth2:** Using OAuth 2 for authentication is a two-stage process. First you use the Project API Key and Secret to create an access token, and then you include the access token in a Authorization header on your API request. The value of the Authorization header should be 'Bearer', a space, and then the access token. See the [OAuth 2 API documentation](https://osdatahub.os.uk/docs/oauth2/overview) for detailed instructions on how to create an access token.


### Encryption

As of October 2018, all calls must be made using a secure hypertext encryption \(HTTPS\).

Ordnance Survey APIs no longer support calls made using SSL v2/v3 or TLS v1.0/v1.1. Thus, all calls made to any of our APIs must support TLS v1.2 as of October 2018 in line with current cyber security recommendations.

### Transformation

Customers should use a transformation utilising the OSTN15/OSGM15 transformation to transform data between EPSG:27700 and EPSG:3857 when intending to use the data with this service.

Data transformed using the old OSTN02/OSGM02 transformation will result in a small but noticeable shift in the data when overlaid.

This is only applicable if you are transforming data held in either EPSG:3857 or EPSG:27700 to be shown on a basemap of the opposite projection.

### Response Codes

| Code | Official description | Explanation in context of the API |
| :--- | :--- | :--- |
| 200 | OK | Request has been successful |
| 304 | Not Modified | In response to a conditional GET request this response indicates that the underlying data has not changed since the previous request, and cached results may be re-used |
| 400 | Bad request | E.g. missing query parameter, malformed syntax |
| 401 | Unauthorized | The client has not provided authentication or incorrect authentication |
| 403 | Forbidden | The client has authenticated its access but does not have sufficient rights to complete the request. |
| 404 | Not found | The server has not found anything matching the Request-URI. |
| 405 | Method not allowed | Request used an unsupported HTTP method, e.g. DELETE or PUT. |
| 429 | Too many requests | Exceeded the number of requests per minute \(rate-limit\). |
| 500 | Internal server error | Generic internal server error. |
| 503 | Service unavailable | Temporary outage due to overloading or maintenance. |

### Content

Through OS Vector Tile API you can connect to different layers for different use cases, including a detailed basemap and several data overlays.

The map features don’t contain the complete list of attribution from the full data products – we have selected attribution that is useful for visualisation. The inclusion of unique IDs where available allow you to cross reference with the full product e.g. using OS Features API.

**Basemap** \(OS OpenData and Premium data\) – This is a detailed OS basemap made from [OS Open Zoomstack](https://www.ordnancesurvey.co.uk/business-government/products/open-zoomstack) and [OS MasterMap Topography Layer](https://www.ordnancesurvey.co.uk/business-government/products/mastermap-topography).

The OS MasterMap Topography Layer building features have a property called ‘RelHMax’ \(height from the ground to the top of the building\) which you can use to extrude and create 3D buildings.

API Endpoint: [https://api.os.uk/maps/vector/v1/vts](https://api.os.uk/maps/vector/v1/vts)

#### Data Overlays

The following layers can be used as overlays to the basemap to add additional information. To access them, add the layer name to the endpoint as described below e.g. https://api.os.uk/maps/vector/v1/vts/{layer-name}

**Boundaries** \(OS OpenData\) - This is a polygon layer made from [Boundary-Line](https://www.ordnancesurvey.co.uk/business-government/products/boundaryline)  which can be used for identifying boundaries \(e.g. Counties, Districts and Parishes\) and creating choropleth map overlays.

API Endpoint: [https://api.os.uk/maps/vector/v1/vts/boundaries](https://api.os.uk/maps/vector/v1/vts/boundaries)

**Greenspace** \(Premium data\) - This is a polygon layer made from [OS MasterMap Greenspace Layer](https://www.ordnancesurvey.co.uk/business-government/products/mastermap-greenspace)  - Britain’s most comprehensive dataset of urban greenspaces.

API Endpoint: [https://api.os.uk/maps/vector/v1/vts/greenspace](https://api.os.uk/maps/vector/v1/vts/greenspace)

**Sites** \(Premium data\) - This is a polygon layer made from [OS MasterMap Sites Layer](https://www.ordnancesurvey.co.uk/business-government/products/mastermap-topography). Contains the site extents for key sites such as schools, hospitals and train stations and their main access points.

API Endpoint: [https://api.os.uk/maps/vector/v1/vts/sites](https://api.os.uk/maps/vector/v1/vts/sites)

**Water** \(Premium data\) - This is a line layer made from [OS MasterMap Water Network Layer](https://www.ordnancesurvey.co.uk/business-government/products/mastermap-water). Contains detailed centre lines following the curve of the waterways precisely, including rivers, streams and canals.

API Endpoint: [https://api.os.uk/maps/vector/v1/vts/water](https://api.os.uk/maps/vector/v1/vts/water)

**Highways** \(Premium data\) - This is a line layer made from [OS MasterMap Highways Network](https://www.ordnancesurvey.co.uk/business-government/products/mastermap-highways). Contains detailed centre lines for roads, paths and ferry routes and includes the links that connect them.

API Endpoint: [https://api.os.uk/maps/vector/v1/vts/highways](https://api.os.uk/maps/vector/v1/vts/highways)

**Paths** \(Premium data\) - This is a line layer made from [OS Detailed Path Network](https://www.ordnancesurvey.co.uk/business-government/products/path-network)  - a connected path network covering Britain’s National Parks.

API Endpoint: [https://api.os.uk/maps/vector/v1/vts/paths](https://api.os.uk/maps/vector/v1/vts/paths)

### Operation

OS Vector Tile API has three main RESTful endpoints. These can be built into your web application or explored individually using a web-browser.

#### Service Metadata

This service is available as a GET resource method allowing you to discover the service metadata.

When generating your key using the OS Data Hub, a URL will be automatically generated using your new API key. For demonstration purposes we have provided a stripped-down URL below: [https://api.os.uk/maps/vector/v1/vts?srs=27700&key=](https://api.os.uk/maps/vector/v1/vts?srs=27700&key=)

| Parameter | Required? | Value |
| :--- | :--- | :--- |
| key  | required | The API Key provided by the OS Data Hub. |
| srs | optional | The Spatial Reference System for the service. The options available are 27700 & 3857. The service defaults to 27700. |

### Styling

This service is available as a GET resource method allowing you to discover the compatible style sheets for the service. It is also possible, when creating a service, to create your own styling. To help you get started, you can find some alternative stylesheets in [this GitHub repository](https://github.com/OrdnanceSurvey/OS-Vector-Tile-API-Stylesheets).

When generating your key using the OS Data Hub, a URL will be automatically generated using your new API key. For demonstration purposes we have provided a stripped-down URL below: [https://api.os.uk/maps/vector/v1/vts/resources/styles?srs=27700&key=](https://api.os.uk/maps/vector/v1/vts/resources/styles?srs=27700&key=)

| Parameter | Required? | Value |
| :--- | :--- | :--- |
| key | required | The API Key provided by the OS Data Hub |
| srs | optional | The Spatial Reference System for the service. The options available are 27700 & 3857. The service defaults to 27700. |

### Tile Request

This service is available as a GET resource method allowing you to access and download the data for a specific tile. If done using a web-browser you will be required to input the z, y, and x coordinates manually.

The request will return the specified tile as a .pbf \(Protocolbuffer Binary Format\).

When generating your key using the OS Data Hub, a URL will be automatically generated using your new API key. For demonstration purposes we have provided a stripped-down URL below: [https://api.os.uk/maps/vector/v1/vts/tile/{z}/{y}/{x}.pbf?srs=27700&key=](https://api.os.uk/maps/vector/v1/vts/tile/{z}/{y}/{x}.pbf?srs=27700&key=)

| Parameter | Required? | Value |
| :--- | :--- | :--- |
| key | required | The API Key provided by the OS Data Hub. |
| srs | optional | The Spatial Reference System for the service. Tthe options available are 27700 & 3857. The service defaults to 27700. |

## What next?

For further reading on the OS Vector Tile API, refer to the [getting started guide](https://osdatahub.os.uk/docs/vts/gettingStarted) or check out [code examples](https://labs.os.uk/public/os-data-hub-examples/os-vector-tile-api/).

