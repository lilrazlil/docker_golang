FROM rivee/golang-base-build-curl:latest AS builder

WORKDIR /go/app

COPY /docker-go-2 .

RUN go mod tidy

RUN cd cmd/db/ && go build .

FROM rivee/alpine_curl AS runner

WORKDIR /database

WORKDIR /go

COPY --from=builder /go/app/cmd/db/db ./

VOLUME [ "/database" ]

CMD [ "./db" ]

EXPOSE 8082