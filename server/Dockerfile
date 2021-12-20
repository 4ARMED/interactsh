FROM golang:alpine AS builder

RUN go install -v github.com/projectdiscovery/interactsh/cmd/interactsh-server@v0.0.7

FROM alpine AS interactsh

COPY --from=builder /go/bin/interactsh-server /

ENTRYPOINT ["/interactsh-server"]
