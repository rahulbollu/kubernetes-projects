# recommendationservice/Dockerfile
FROM golang:1.21-alpine AS builder
WORKDIR /app
COPY . .
RUN go build -o recommendationservice .

FROM alpine:latest
WORKDIR /app
COPY --from=builder /app/recommendationservice .
EXPOSE 8080
ENTRYPOINT ["./recommendationservice"]
