# Proto Module

Protobuf definitions and generated Go code for inter-service gRPC communication.

## Generation

```bash
# PATH must include $(go env GOPATH)/bin for protoc-gen-go and protoc-gen-go-grpc
export PATH="$PATH:$(go env GOPATH)/bin"
./scripts/proto-gen.sh

# Or from repo root:
make proto
```

## Key Files

| Path | Purpose |
|---|---|
| `core.proto` | gRPC service and message definitions |
| `gen/corepb/` | Generated Go code (do not edit manually) |

## gRPC Services Defined

- **StatusService** — used by `public`
- **WorkerService** — used by `worker`
- **AlerterService** — used by `alerter`

## Module Setup

Each Go service's `go.mod` has a `replace` directive pointing to this local `proto/` module. When adding a new Go service, replicate this pattern.

## Versions

- gRPC v1.68.0
- protobuf v1.35.2
- protoc-gen-go-grpc v1.6.1
