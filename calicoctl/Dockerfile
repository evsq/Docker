FROM jeanblanchard/alpine-glibc
MAINTAINER Tom Denham <tom@projectcalico.org>
WORKDIR /
COPY . .

RUN chmod +x calicoctl
RUN mv calicoctl /bin/calicoctl

ENV CALICO_CTL_CONTAINER=TRUE

ENTRYPOINT ["/bin/calicoctl"]
