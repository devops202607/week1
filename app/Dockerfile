FROM golang:1.22-alpine AS build
WORKDIR /app
COPY app/ .
RUN go build -o server main.go

FROM alpine:3.19
WORKDIR /app
COPY --from=build /app/server .
COPY app/ .
EXPOSE 8080
CMD ["./server"]
