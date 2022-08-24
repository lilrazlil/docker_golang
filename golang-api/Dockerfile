FROM rivee/golang-base-build-curl:latest AS builder

WORKDIR /go/app

COPY /docker-go-1 .

RUN go mod tidy 

RUN cd cmd/api && go build .


FROM rivee/alpine_curl as runner

WORKDIR /go

COPY --from=builder /go/app/cmd/api/api ./

EXPOSE 8081

CMD [ "./api" ]