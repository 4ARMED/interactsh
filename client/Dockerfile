FROM golang:alpine AS builder

RUN GO111MODULE=on go get -v github.com/projectdiscovery/interactsh/cmd/interactsh-client
RUN GO111MODULE=on go get -v github.com/projectdiscovery/notify/cmd/notify

FROM alpine AS interactsh

COPY --from=builder /go/bin/interactsh-client /
COPY --from=builder /go/bin/notify /

ENTRYPOINT ["/interactsh-client"]
