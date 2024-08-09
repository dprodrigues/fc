FROM golang:latest AS builder

WORKDIR /app
COPY . .
RUN go mod tidy && \
 go build main.go

FROM scratch

WORKDIR /app
COPY --from=builder /app/main .

CMD [ "./main" ]
