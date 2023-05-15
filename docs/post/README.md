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
        Jwt: "YOUR_BEARER_TOKEN_HERE",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.Post != nil {
        // handle response
    }
}
```

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
