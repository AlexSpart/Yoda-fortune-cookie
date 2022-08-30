FROM golang:1.16 AS build
RUN mkdir /app
ADD . /app
WORKDIR /app
COPY * ./
RUN CGO_ENABLED=0 GOOS=linux go build -o frontend .

FROM alpine:latest AS run
COPY --from=build /app/ ./
EXPOSE 8080
CMD ["./frontend"]