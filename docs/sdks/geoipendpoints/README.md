# GeoIPEndpoints
(*geoIPEndpoints()*)

## Overview

Access IP geolocation data in various formats.

### Available Operations

* [getIp](#getip) - Get Current IP Address
* [getIpData](#getipdata) - Get Json Data from IP Address

## getIp

Get Current IP Address

### Example Usage

```java
package hello.world;

import java.lang.Exception;
import org.openapis.openapi.GeoIp;
import org.openapis.openapi.models.operations.GetIpResponse;

public class Application {

    public static void main(String[] args) throws Exception {

        GeoIp sdk = GeoIp.builder()
            .build();

        GetIpResponse res = sdk.geoIPEndpoints().getIp()
                .call();

        if (res.res().isPresent()) {
            // handle response
        }
    }
}
```

### Response

**[GetIpResponse](../../models/operations/GetIpResponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| models/errors/APIException | 4XX, 5XX                   | \*/\*                      |

## getIpData

Get Json Data from IP Address

### Example Usage

```java
package hello.world;

import java.lang.Exception;
import org.openapis.openapi.GeoIp;
import org.openapis.openapi.models.errors.HTTPValidationError;
import org.openapis.openapi.models.operations.GetIpDataResponse;

public class Application {

    public static void main(String[] args) throws HTTPValidationError, Exception {

        GeoIp sdk = GeoIp.builder()
            .build();

        GetIpDataResponse res = sdk.geoIPEndpoints().getIpData()
                .call();

        if (res.responseGetJsonDataJsonGet().isPresent()) {
            // handle response
        }
    }
}
```

### Parameters

| Parameter               | Type                    | Required                | Description             |
| ----------------------- | ----------------------- | ----------------------- | ----------------------- |
| `ipAddress`             | *JsonNullable\<String>* | :heavy_minus_sign:      | N/A                     |

### Response

**[GetIpDataResponse](../../models/operations/GetIpDataResponse.md)**

### Errors

| Error Type                        | Status Code                       | Content Type                      |
| --------------------------------- | --------------------------------- | --------------------------------- |
| models/errors/HTTPValidationError | 422                               | application/json                  |
| models/errors/APIException        | 4XX, 5XX                          | \*/\*                             |