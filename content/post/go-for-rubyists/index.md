---
title: Go for Rubyists [WIP]
date: 2019-10-12
math: false
diagram: true
markup: mmark
draft: true
image:
  placement: 3
  caption: ''
---

**This post is still a work in progress**

I am quite familiar with Go and am starting out with Ruby so not so familiar with it. I decided to write this post to know how certain pieces of Go code can be written in Ruby.

## Classes and their instantiation

Go is not an OO language but it provides constructs to implement some OO behaviour.

Go and other imperative languages provide a struct that can be used to implement OOP-like patterns. Structs are made up of fields (data members in OOP), over these structs we can define methods (member functions in OOP). The constructor (`New` in the below snippet) however is not a method defined over a struct but a function returning an instantiation of the struct (in other words an object of the `Client` class)

```go
struct Client {
       host string
       port string
}

func New(host string, port string) Client {
       return Client{
              host: host,
              port: port,
       }
}
```

```ruby
class Client
  def initialize(host, port)
    @host = host
    @port = port
  end
end
```

## Accessing instance variables

In Go visibility is determined using case. Everything that is upper case will be public and lowercase methods and struct members are private by default.

Lets say we want to introduce a new field to our struct `Client` called `timeout` which will be publicly accessible. **Note:** This struct field will only be accessible to code in other packages if the `Client` struct itself is public in the first place which it is since it is in upper case.

```go
package client

struct Client {
       host    string
       port    string
       Timeout time.Time
}

func New(host string, port string) Client {
       return Client{
              host:    host,
              port:    port,
              Timeout: nil,
       }
}

func (c *Client) GetHost() string {
     return c.host
}
```

The calling code for accessing the public and private members of a struct would look something like this.

```go
package main

import (
    "fmt"
    // import path for our client package
)

c := client.New("127.0.0.1", "5537")
// publicly accessible
fmt.Println(c.Timeout)

// can only be accessed through a method defined on the struct
fmt.Println(c.GetHost())

// this results in an error
fmt.Println(c.port)
```

Whereas in Ruby instance variables are private by default so to be able to access or modify data members we need to using accessors:
- `attr_reader`: if the instance variables are just to be read.
- `attr_writer`: if the instance variables are just to be modified/written to.
- `attr_accessor`: if the instance variables are to be both read or written to.

Methods however, are public by default and need to be explicitly marked as private to prevent them from being exposed.
```ruby
class Client
  attr_accessor: timeout

  def initiliaze(host, port, timeout = nil)
    @host = host
    @port = port
    @timeout = timeout
  end
end

obj = Client.new('127.0.0.1', '5000')
assert(obj.timeout, nil)
obj.timeout = 10 # seconds
puts obj.timeout # returns 10
obj.host # this will return an `undefined method` error since it is private by default
```
