FROM golang:1.10-alpine3.7

RUN apk add --no-cache git

WORKDIR /go/src/github.com/lemeb/ddns
COPY . .
RUN ls 

# RUN go get -u github.com/gin-gonic/gin
RUN echo "we are here"
RUN go get -d -v ./...
RUN go install -v .

ENV GIN_MODE release

CMD /go/bin/ddns --domain=${DDNS_DOMAIN} --soa_fqdn=${DDNS_SOA_DOMAIN} --redis=${DDNS_REDIS_HOST}
