FROM golang:1.19 as builder

WORKDIR /app

COPY . .

RUN CGO_ENABLE=0 GOOS=linux GOARCH=amd64 go build -o server .

FROM alpine:3.16

COPY --from=builder /app/server /

EXPOSE 8080

CMD ["/server"]

