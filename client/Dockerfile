FROM golang:1.23.1

# Port to run GRPC server
ENV HTTP_PORT=8080
EXPOSE ${HTTP_PORT}

ENV PORTS_ADDRESS=ports_service:4040
# ENV PORTS_JSON=/go/client/ports.json
WORKDIR /go

COPY ./client/ ./client

WORKDIR /go/client

RUN go build -o client.exe ./main.go

ENTRYPOINT ./client.exe