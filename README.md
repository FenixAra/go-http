# go-http
HTTP Wrapper in golang along with mock

[![GoDoc](https://godoc.org/github.com/FenixAra/go-http/http?status.svg)](https://godoc.org/github.com/FenixAra/go-http/http)
[![Go Report Card](https://goreportcard.com/badge/github.com/FenixAra/go-http/http)](https://goreportcard.com/report/github.com/FenixAra/go-http/http)

To get the latest package: 

```sh
go get -u github.com/FenixAra/go-http/http
```

## Usage
```
package main

import (
	"net/http"

	http_wrap "github.com/FenixAra/go-http/http"
	"github.com/FenixAra/go-util/log"
)

func main() {
	config := log.NewConfig("", "Debug", "Full", "TestApp", "", "", "")
	l := log.New(config)

	cfg := http_wrap.NewConfig()
	cfg.SetRetries(10)
	cfg.SetTimeout(5)
	wrapper := http_wrap.New(cfg, l)

	wrapper.MakeRequest(http.MethodGet, "https://www.google.com", "Google", nil, nil)
}
```