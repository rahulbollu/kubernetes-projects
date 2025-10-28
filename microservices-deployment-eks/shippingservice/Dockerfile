# shippingservice/Dockerfile
FROM golang:1.21-alpine AS builder
WORKDIR /app
COPY . .
RUN go build -o shippingservice .

FROM alpine:latest
WORKDIR /app
COPY --from=builder /app/shippingservice .
EXPOSE 8080
ENTRYPOINT ["./shippingservice"]