# The Cloudflare Turnstile Go Server Side Client

Turnstile is a service that allows you to protect your web applications from abuse. It is a Cloudflare service that is currently in private beta. You can read more about it [here](https://developers.cloudflare.com/turnstile/).

## Installation

```bash
go get github.com/ssibrahimbas/turnstile
```

## Documentation

[![Go Reference](https://pkg.go.dev/badge/github.com/ssibrahimbas/turnstile.svg)](https://pkg.go.dev/github.com/ssibrahimbas/turnstile)

## Usage

```go
package main

import (
    "context"
    "github.com/ssibrahimbas/turnstile"
)

func main() {
    ctx := context.Background()
    srv := turnstile.New(turnstile.Config{
        Secret: "your-secret",
    })
    ok, err := srv.Verify(ctx, "your-token", "your-ip")
    if err != nil {
        panic(err)
    }
    if !ok {
        panic("token is not valid")
    }
    println("token is valid")
}
```

## Contributing

Contributions are always welcome!

## License

[MIT](https://choosealicense.com/licenses/mit/)
