FROM golang:1.23.1

# Port to run GRPC server
ENV HTTP_PORT=8080
EXPOSE ${HTTP_PORT}

ENV PORTS_ADDRESS=ports_service:4040
# ENV PORTS_JSON=/go/client/ports.json
WORKDIR /go

COPY ./server/ ./server

WORKDIR /go/server

RUN go build -o server.exe ./main.go

ENTRYPOINT ./server.exe