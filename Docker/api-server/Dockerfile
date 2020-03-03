FROM golang:alpine AS builder

WORKDIR /go/src/

RUN apk update && \
    apk add git && \
    git clone https://github.com/op19-it-edu/api-server.git

WORKDIR /go/src/api-server

RUN go mod download && \
    GOOS=linux GOARCH=amd64 CGO_ENABLED=0 \
    go build -o main server.go

ENV GO111MODULE=on

FROM alpine

COPY --from=builder /go/src/api-server/main /go/src/api-server/main

WORKDIR /go/src/api-server

ENTRYPOINT ["./main"]

EXPOSE 1323
