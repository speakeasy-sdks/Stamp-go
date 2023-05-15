# StampApi

<!-- Start SDK Installation -->
## SDK Installation

```bash
go get github.com/speakeasy-sdks/Stamp-go
```
<!-- End SDK Installation -->

## SDK Example Usage
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

<!-- Start SDK Available Operations -->
## Available Resources and Operations


### [Auth](docs/auth/README.md)

* [LogIn](docs/auth/README.md#login) - log in or sign up to stamp with an external auth provider
* [RefreshToken](docs/auth/README.md#refreshtoken) - exchange token in header for a new one

### [Post](docs/post/README.md)

* [CreatePost](docs/post/README.md#createpost) - create a new post
* [GetRecentPosts](docs/post/README.md#getrecentposts) - get a list of most recent posts
<!-- End SDK Available Operations -->

### Maturity

This SDK is in beta and therefore, we recommend pinning usage to a specific package version.
This way, you can install the same version each time without breaking changes unless you are intentionally
looking for the latest version.

### Contributions

While we value open-source contributions to this SDK, this library is generated and maintained programmatically.
Feel free to open a PR or a Github issue as a proof of concept and we'll do our best to include it in a future release !

### SDK Created by [Speakeasy](https://docs.speakeasyapi.dev/docs/using-speakeasy/client-sdks)
