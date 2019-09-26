FROM alpine

RUN apk --update add bind-tools ca-certificates openssl && update-ca-certificates && rm -rf /var/cache/apk/*

ADD coredns /coredns

EXPOSE 53 53/udp

ENTRYPOINT ["/coredns"]
