# connect-go-example

This is a repo to familiarise myself with the autogenerated code from the `connect-go` [package](https://connectrpc.com/docs/go/getting-started/).

### Instructions

1. The server can be run by `go run cmd/server/main.go`
2. The client can be run via `go run cmd/client/main.go` (with the server running)

Curl requests can be made to the server via:
```sh
$ curl \
    --header "Content-Type: application/json" \
    --data '{"name": "Jane"}' \
    http://localhost:8080/greet.v1.GreetService/Greet
```
We can also use `grpcurl` to make gRPC calls (the server does not have reflection enabled)
```sh
$ grpcurl \
    -proto ./greet/v1/greet.proto \
    -plaintext \
    -d '{"name": "Jane"}' \
    localhost:8080 greet.v1.GreetService/Greet
```
