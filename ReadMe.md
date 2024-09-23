Compiles using docker build -f server/Dockerfile -t prog .

go build -o client.exe main.go
./client.exe

Hello, World! This is a client.
2024/09/17 18:49:18 user: Sean

./client.exe PORTS_GRPC_PORT=localhost:50051

grpcui localhost:50051
Failed to dial target host "localhost:50051": tls: first record does not look like a TLS handshake

2024/09/17 20:11:16 INFO: [core] [Channel #1 SubChannel #2] Subchannel created
2024/09/17 20:11:16 INFO: [core] [Channel #1] Channel Connectivity change to CONNECTING
2024/09/17 20:11:16 INFO: [core] [Channel #1] Channel exiting idle mode
2024/09/17 20:11:16 INFO: [core] [Channel #1 SubChannel #2] Subchannel Connectivity change to CONNECTING
2024/09/17 20:11:16 INFO: [core] [Channel #1 SubChannel #2] Subchannel picks a new address "localhost:50051" to connect
2024/09/17 20:11:16 INFO: [core] [pick-first-lb 0xc00005c480] Received SubConn state update: 0xc00005c600, {ConnectivityState:CONNECTING ConnectionError:<nil>}
Failed to dial target host "localhost:50051": tls: first record does not look like a TLS handshake2024/09/17 20:11:16 INFO: [core] Creating new client transport to "{Addr: \"localhost:50051\", ServerName: \"localhost:50051\", }": connection error: desc = "transport: authentication handshake failed: tls: first record does not look like a TLS handshake"


go install github.com/fullstorydev/grpcurl/cmd/grpcurl@latest
grpcurl -plaintext localhost:50051 list
grpcurl -plaintext localhost:50051 describe

https://github.com/fullstorydev/grpcurl/issues/200 says use plaintext when not using TLS
