# -----------
# build環境
# -----------
FROM golang:1.22.0-alpine3.19 as builder

# ログに出力する時間をJSTにするため、タイムゾーンを設定
ENV TZ /usr/share/zoneinfo/Asia/Tokyo

WORKDIR /app
COPY ./ /app

RUN apk update && apk add git
RUN go install github.com/cosmtrek/air@v1.51.0
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
