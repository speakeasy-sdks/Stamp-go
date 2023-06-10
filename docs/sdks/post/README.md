# Post

### Available Operations

* [CreatePost](#createpost) - create a new post
* [GetRecentPosts](#getrecentposts) - get a list of most recent posts

## CreatePost

create a new post

### Example Usage

```go
package main

import(
	"context"
	"log"
	"StampApi"
	"StampApi/pkg/models/shared"
	"StampApi/pkg/models/operations"
)

func main() {
    s := stampapi.New()

    ctx := context.Background()
    res, err := s.Post.CreatePost(ctx, shared.PostPostRequest{
        Description: "unde",
        Link: "nulla",
        RootDomain: "corrupti",
        Title: "Dr.",
    }, operations.CreatePostSecurity{
        Jwt: "",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.Post != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                      | Type                                                                           | Required                                                                       | Description                                                                    |
| ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| `ctx`                                                                          | [context.Context](https://pkg.go.dev/context#Context)                          | :heavy_check_mark:                                                             | The context to use for the request.                                            |
| `request`                                                                      | [shared.PostPostRequest](../../models/shared/postpostrequest.md)               | :heavy_check_mark:                                                             | The request object to use for the request.                                     |
| `security`                                                                     | [operations.CreatePostSecurity](../../models/operations/createpostsecurity.md) | :heavy_check_mark:                                                             | The security requirements to use for the request.                              |


### Response

**[*operations.CreatePostResponse](../../models/operations/createpostresponse.md), error**


## GetRecentPosts

get a list of most recent posts

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
    res, err := s.Post.GetRecentPosts(ctx, operations.GetRecentPostsRequest{
        LastFetchedItemID: stampapi.String("vel"),
        Size: stampapi.Int(623564),
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.PostResultSet != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                            | Type                                                                                 | Required                                                                             | Description                                                                          |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ |
| `ctx`                                                                                | [context.Context](https://pkg.go.dev/context#Context)                                | :heavy_check_mark:                                                                   | The context to use for the request.                                                  |
| `request`                                                                            | [operations.GetRecentPostsRequest](../../models/operations/getrecentpostsrequest.md) | :heavy_check_mark:                                                                   | The request object to use for the request.                                           |


### Response

**[*operations.GetRecentPostsResponse](../../models/operations/getrecentpostsresponse.md), error**

