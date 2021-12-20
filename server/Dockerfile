FROM golang:alpine AS builder

RUN GO111MODULE=on go get -v github.com/projectdiscovery/interactsh/cmd/interactsh-server@v0.0.7

FROM alpine AS interactsh

COPY --from=builder /go/bin/interactsh-server /

ENTRYPOINT ["/interactsh-server"]
