FROM golang:1.17-alpine AS build

WORKDIR /app

COPY go.mod ./
COPY *.go ./

RUN go mod download && \
    go build -o /gocheck

FROM scratch

WORKDIR /

COPY --from=build /gocheck /gocheck

EXPOSE 8080

ENTRYPOINT [ "/gocheck" ]

