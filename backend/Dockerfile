# -----------
# build環境
# -----------
FROM golang:1.22.0-alpine3.19 as builder

ENV CGO_ENABLED=0
ENV GOOS=linux
ENV GOARCH=amd64
# ログに出力する時間をJSTにするため、タイムゾーンを設定
ENV TZ /usr/share/zoneinfo/Asia/Tokyo

WORKDIR /app
COPY ./ /app

RUN go install github.com/cosmtrek/air@v1.27.3
RUN go install github.com/ramya-rao-a/go-outline@latest
RUN go install golang.org/x/tools/gopls@latest

RUN go build -o main ./main.go

EXPOSE 8080

# -----------
# production環境
# -----------
FROM alpine as production
RUN apk update && apk upgrade
RUN mkdir /app
WORKDIR /app

COPY --from=builder /app/main ./main

CMD ["./main"]
