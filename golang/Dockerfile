FROM golang:1.12-alpine as go-build

WORKDIR /go/src/github.com/someproject

COPY . .

RUN VERSION=$(git rev-parse --short HEAD) CGO_ENABLED=0 go build -ldflags "-X main.version=${VERSION}" -o someproject cmd/*.go

FROM debian:10.1

COPY --from=go-build /go/src/github.com/someproject /etc/someproject

ENV SOME_LOGIN="" \
    SOME_PASSWORD=""

RUN mkdir /var/lib/someproject && \
    mkdir /var/log/someproject

EXPOSE 80

CMD ["someproject"]
