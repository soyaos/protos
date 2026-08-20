<p align="center">
  <img src="assets/logo.png" alt="SoyaOS" width="120" height="120" />
</p>

# soyaos/protos

Protocol buffer definitions for the SoyaOS surface area. **Source of truth** for code generation in every official SDK:

- Go SDK — embedded in [soyaos/soyaos](https://github.com/soyaos/soyaos) at `api/`
- TypeScript SDK — `soyaos/sdk-ts` (planned)
- Python SDK — `soyaos/sdk-python` (planned)

Wire transport is [Connect-Go](https://connectrpc.com) — every service is reachable as Connect, gRPC, and gRPC-Web on the same port. See the **SoyaOS GitHub repository plan** for the rationale.

## Layout (planned)

```
proto/
├── soyaos/v1/
│   ├── kernel/        # SoyaKernel  (LLM routing, chat completions)
│   ├── orbit/         # node registry, bootstrap tokens
│   ├── dispatcher/    # task scheduling, DAG
│   ├── memory/        # SoyaMemory (working/episodic/semantic/procedural)
│   ├── tooling/       # MCP / A2A tool registry
│   ├── auth/          # capability tokens, identity
│   ├── scope/         # observability, replay
│   ├── connectors/    # Channel Connectors (DD-006)
│   ├── scheduler/     # cron + one-shot scheduler (DD-007)
│   ├── artifact/      # 6-form Artifact abstraction (proposed DD-012)
│   └── factory/       # Agent Factory (DD-009)
```

This repo will be wired with [`buf`](https://buf.build) for lint, breaking-change detection, and SDK generation. Day-1 placeholder — schemas land before NewsBeam (DD-009).

## License

[MIT](https://github.com/soyaos/soyaos/blob/main/LICENSE) — Copyright (c) 2026 SoyaOS Contributors.
