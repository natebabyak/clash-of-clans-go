# clash-of-clans-go

A Go client for the Clash of Clans API.

## Features

- Full API coverage
- Fully typed
- Near-zero performance overhead

## Getting Started

1. [Register for access to the Clash of Clans API](https://developer.clashofclans.com/sign-in#/register).

2. [Create a Clash of Clans API key](https://developer.clashofclans.com/account#/new-key)

```bash
go get github.com/natebabyak/clash-of-clans-go
```

```go
package main

import (
    "context"
    "fmt"
    "os"

    "github.com/natebabyak/clash-of-clans-go"
)

func main() {
    client, err := coc.NewClient()
    if err != nil {
        log.Fatal(err)
    }

    ctx := context.Background()

    clan, err := client.Clans.Get(ctx, "#1234567890")
    if err != nil {
        log.Fatal(err)
    }

    fmt.Printf("%s has %d members!\n", clan.Name, clan.Members)
}
```

```go
client, err := coc.NewClient(
    coc.WithKey(os.Getenv("CLASH_TOKEN")),
)
```

## Legal

Usage is subject to Supercell's Terms and Conditions.

This material is unofficial and is not endorsed by Supercell. For more information see Supercell's Fan Content Policy: [www.supercell.com/fan-content-policy](https://www.supercell.com/fan-content-policy).

## License

MIT
