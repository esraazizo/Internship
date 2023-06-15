FROM golang:1.16.5-alpine3.14

WORKDIR /app

COPY . .

RUN go build -o main .

EXPOSE 9090

CMD ["./main"]
