<!-- Start SDK Example Usage [usage] -->
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
<!-- End SDK Example Usage [usage] -->