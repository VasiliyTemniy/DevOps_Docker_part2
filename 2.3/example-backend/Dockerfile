FROM golang:1.20.3-bullseye AS base

EXPOSE 8080

WORKDIR /usr/src/app

COPY go.mod go.mod
COPY go.sum go.sum


FROM base AS build-stage

COPY . .

RUN go build

RUN go test ./...

CMD ./server