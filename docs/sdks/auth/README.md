# Auth

### Available Operations

* [LogIn](#login) - log in or sign up to stamp with an external auth provider
* [RefreshToken](#refreshtoken) - exchange token in header for a new one

## LogIn

log in or sign up to stamp with an external auth provider, returns a jwt for accessing stamp api.

### Example Usage

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
        AccessToken: "distinctio",
        AuthProvider: "quibusdam",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.LogInResponse != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                  | Type                                                       | Required                                                   | Description                                                |
| ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- |
| `ctx`                                                      | [context.Context](https://pkg.go.dev/context#Context)      | :heavy_check_mark:                                         | The context to use for the request.                        |
| `request`                                                  | [shared.LogInRequest](../../models/shared/loginrequest.md) | :heavy_check_mark:                                         | The request object to use for the request.                 |


### Response

**[*operations.LogInResponse](../../models/operations/loginresponse.md), error**


## RefreshToken

exchange token in header for a new one

### Example Usage

```go
package main

import(
	"context"
	"log"
	"StampApi"
	"StampApi/pkg/models/operations"
)

func main() {
    s := stampapi.New()

    ctx := context.Background()
    res, err := s.Auth.RefreshToken(ctx, operations.RefreshTokenSecurity{
        Jwt: "",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.RefreshTokenResponse != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                          | Type                                                                               | Required                                                                           | Description                                                                        |
| ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| `ctx`                                                                              | [context.Context](https://pkg.go.dev/context#Context)                              | :heavy_check_mark:                                                                 | The context to use for the request.                                                |
| `security`                                                                         | [operations.RefreshTokenSecurity](../../models/operations/refreshtokensecurity.md) | :heavy_check_mark:                                                                 | The security requirements to use for the request.                                  |


### Response

**[*operations.RefreshTokenResponse](../../models/operations/refreshtokenresponse.md), error**

