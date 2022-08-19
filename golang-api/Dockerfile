FROM rivee/golang-base-build-curl:latest

ENV API_PORT 8081

ARG STAMP

WORKDIR /go

COPY /docker-go-1 ./app

RUN cd app/ && go mod tidy

RUN cd /go/app/cmd/api/ && go build -o /go/app/api

ENTRYPOINT [ "/go/app/api" ]  

EXPOSE 8081
