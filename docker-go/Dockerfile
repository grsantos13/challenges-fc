FROM golang:1.17.2-alpine3.14 AS builder

WORKDIR /app

COPY . /app
RUN CGO_ENABLED=0 GOOS=linux GOARCH=arm go build -o app main.go

FROM scratch

WORKDIR /app

COPY --from=builder /app/app /app/app

CMD ["./app"]