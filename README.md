# proto-gen-typescript

Generated TypeScript bindings (protobuf-es v2) for the shared protobuf
schemas defined in
[`altessa-s/proto`](https://github.com/altessa-s/proto). Do not edit
files in this repository by hand — they are regenerated and pushed
automatically on every push to `main` / `develop` and every `vX.Y.Z` tag.

## Install

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
- `@connectrpc/connect` — Connect RPC runtime (and a transport package
  like `@connectrpc/connect-web` / `@connectrpc/connect-node`)

## Packages

| Proto package | Module path |
|---------------|-------------|
| `io.altessa.badrequest.v1` | `@altessa-s/proto-gen-typescript/badrequest/v1/badrequest_pb.js` |
| `io.altessa.serviceinfo.v1` | `@altessa-s/proto-gen-typescript/serviceinfo/v1/serviceinfo_pb.js` |

## License

MIT — see [LICENSE](LICENSE).
