# Stage 1: Build Stage
FROM golang:1.17 AS builder
ENV GO111MODULE=on \
    CGO_ENABLED=0 \
    GOOS=linux \
    GOARCH=amd64
WORKDIR /build
COPY go.mod go.sum ./
RUN go mod download
COPY . .
RUN go build -o app ./cmd/api

# Stage 2: Production Stage
FROM scratch
COPY --from=builder /build/app /
ENTRYPOINT ["/app"]
