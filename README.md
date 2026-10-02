# IP-Max OpenAPI

The OpenAPI 3.1 contract for the [IP-Max API](https://ipm.ax) and the response fixtures every official SDK is tested against.

| File | Contents |
| --- | --- |
| `openapi.json` | Endpoints, authentication and all 67 schemas |
| `fixtures/*.json` | Real responses captured from the server as `{ status, headers, body }`, each validated against `openapi.json` |

The schemas are exported from the server's own response types, so they describe exactly what goes over the wire.

## Endpoints

| Method | Path | Auth | Billed |
| --- | --- | --- | --- |
| `GET` | `/api/v1/catalog` | none | no |
| `GET` | `/api/v1/account` | API key | no |
| `POST` | `/api/v1/geoip` | API key | yes |
| `POST` | `/api/v1/intelligence` | API key | yes |

Base URL: `https://api.ipm.ax`. Send the key as `Authorization: Bearer <key>`. Billed lookups require an `Idempotency-Key` header; reuse it when retrying so a request is never charged twice.

## SDKs

| Language | Package | Repository |
| --- | --- | --- |
| TypeScript | [`ipmax`](https://www.npmjs.com/package/ipmax) | [typescript-sdk](https://github.com/IPMaxxing/typescript-sdk) |
| Python | [`ipmax`](https://pypi.org/project/ipmax/) | [python-sdk](https://github.com/IPMaxxing/python-sdk) |
| Go | [`github.com/IPMaxxing/go-sdk`](https://pkg.go.dev/github.com/IPMaxxing/go-sdk) | [go-sdk](https://github.com/IPMaxxing/go-sdk) |
| Rust | [`ipmax`](https://crates.io/crates/ipmax) | [rust-sdk](https://github.com/IPMaxxing/rust-sdk) |
| PHP | [`ipmax/ipmax`](https://packagist.org/packages/ipmax/ipmax) | [php-sdk](https://github.com/IPMaxxing/php-sdk) |
| .NET | [`IPMax`](https://www.nuget.org/packages/IPMax) | [dotnet-sdk](https://github.com/IPMaxxing/dotnet-sdk) |
| Ruby | [`ipmax`](https://rubygems.org/gems/ipmax) | [ruby-sdk](https://github.com/IPMaxxing/ruby-sdk) |

## License

[Apache-2.0](LICENSE)
