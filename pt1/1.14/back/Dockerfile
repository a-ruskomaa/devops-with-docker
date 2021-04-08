FROM golang:1.16-alpine

WORKDIR /usr/src/app

EXPOSE 8080

COPY . .

RUN apk add build-base

ENV PORT=8080

ENV REQUEST_ORIGIN="http://localhost:5000"

RUN go build

RUN go test ./...

CMD [ "./server" ]