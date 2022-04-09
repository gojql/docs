Getting Started
===============
JQL is a Go package that provides a fast and [simple](#get-a-value) way to get values from a json object.
It has features such as [one line retrieval](#get-a-value), [dot notation paths](#path-syntax), [iteration](#iterate-through-an-object-or-array), and [parsing json lines](#json-lines).


This README is a quick overview of how to use JQL, for more information check out [JQL Syntax](SYNTAX.md).

## Installing

To start using JQL, install Go and run `go get`:

```sh
$ go get -u github.com/gojql/core
```

This will retrieve the library.

## Get a value
Get searches json for the specified path. A path is in dot syntax, such as "name.last" or "age". When the value is found it's returned immediately. 

```go
package main

import "github.com/gojql/core"

const json = `{"book":{
  "id": 9,
  "title": "Infinix",
  "description": "Infinix Inbook X1 Ci3 10th 8GB...",
  "price": 1099,
  "thumbnail": "https://dummyjson.com/image/i/products/9/thumbnail.jpg"
}}`

func main() {
	value := jql.Query(json, "#title")
	println(value.String())
}
```

Prints:

```
Infinix
```


