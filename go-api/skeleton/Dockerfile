FROM golang:1.25-alpine AS build
WORKDIR /src
COPY . .
RUN go build -o /app ./main.go

FROM gcr.io/distroless/static
COPY --from=build /app /app
ENTRYPOINT ["/app"]
