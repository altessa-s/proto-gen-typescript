# proto-gen-typescript

Generated TypeScript bindings (protobuf-es v2) for the
[altessa-s/proto](https://github.com/altessa-s/proto) schema.

This repository is auto-generated. Do not edit its files by hand — they are
regenerated from [`altessa-s/proto`](https://github.com/altessa-s/proto) and
pushed automatically on every push to `main` / `develop` and every `vX.Y.Z`
tag. The only hand-maintained file is this `README.md`.

## Installation

Configure `.npmrc` with the GitHub Packages scope:

```
@altessa-s:registry=https://npm.pkg.github.com
//npm.pkg.github.com/:_authToken=${GITHUB_TOKEN}
```

Then:

```
npm install @altessa-s/proto-gen-typescript          # latest stable
npm install @altessa-s/proto-gen-typescript@develop  # develop track
npm install @altessa-s/proto-gen-typescript@main     # main track
```

Peer runtime dependencies:

- `@bufbuild/protobuf` — protobuf-es runtime
- `@connectrpc/connect` — Connect RPC runtime (and a transport package like
  `@connectrpc/connect-web` / `@connectrpc/connect-node`)

## Packages

Each proto file is a separate `*_pb.js` module, importable via its subpath.

| Proto package | Module path | Description |
|---|---|---|
| `io.altessa.badrequest.v1` | `@altessa-s/proto-gen-typescript/io/altessa/badrequest/v1/badrequest_pb.js` | `BadRequest` / `FieldViolation` error-detail payload for a `google.rpc.Status` with `INVALID_ARGUMENT`. |
| `io.altessa.serviceinfo.v1` | `@altessa-s/proto-gen-typescript/io/altessa/serviceinfo/v1/serviceinfo_pb.js` (and `serviceinfo_service_pb.js`) | `ServiceInfo` runtime metadata plus the `ServiceInfoService.GetServiceInfo` introspection RPC. |
| `io.altessa.type.v1` | `@altessa-s/proto-gen-typescript/io/altessa/type/v1/*_pb.js` (one file per type) | General-purpose, domain-neutral value types (`Contact`, `DatePeriod`, `FileRef`, …) reused across services. |

## Usage

```ts
import { create } from "@bufbuild/protobuf";
import { ServiceInfoSchema } from "@altessa-s/proto-gen-typescript/io/altessa/serviceinfo/v1/serviceinfo_pb.js";

const info = create(ServiceInfoSchema, {
    serviceName: "billing-api",
    fullVersion: "1.4.2+build.873",
});
```

The `ServiceInfoService` gRPC service and its single
`GetServiceInfo(GetServiceInfoRequest) returns (GetServiceInfoResponse)` RPC are
exported from `serviceinfo_service_pb.js` for use with a Connect transport.

## Versioning

Versions track [`altessa-s/proto`](https://github.com/altessa-s/proto): a
`vX.Y.Z` tag on the schema repo produces the same release here, and the
`main` / `develop` branches follow the matching schema branches.

## Contributing

This repository contains generated output only. To change what appears here,
edit the schemas or generation config in
[`altessa-s/proto`](https://github.com/altessa-s/proto); the next sync
regenerates and republishes these bindings.

## License

MIT — see [LICENSE](LICENSE).
