FROM golang:1.8-alpine
ADD . /go/src/api-app
RUN go get github.com/gorilla/mux
RUN go install api-app

FROM alpine:latest
COPY --from=0 /go/bin/api-app .
ENV PORT 8080
CMD ["./api-app"]
