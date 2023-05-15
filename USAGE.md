<!-- Start SDK Example Usage -->
```go
package main

import(
	"context"
	"log"
	"StampApi"
	"StampApi/pkg/models/shared"
)

func main() {
    s := stampapi.New()

    ctx := context.Background()
    res, err := s.Auth.LogIn(ctx, shared.LogInRequest{
        AccessToken: "corrupti",
        AuthProvider: "provident",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.LogInResponse != nil {
        // handle response
    }
}
```
<!-- End SDK Example Usage -->