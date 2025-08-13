FROM golang:1.19-alpine AS builder

WORKDIR /app

COPY go.mod ./

RUN go mod download

COPY . .

RUN CGO_ENABLED=0 GOOS=linux go build -o ./goServer

FROM scratch

WORKDIR /

COPY --from=builder /app/goServer /goServer

EXPOSE 8080

CMD ["./goServer"]