# @flagbridge/openfeature-provider

[OpenFeature](https://openfeature.dev) provider for [FlagBridge](https://github.com/flagbridge/flagbridge). Lets you use FlagBridge as the evaluation backend behind the OpenFeature SDK standard — so you can swap flag vendors without changing application code.

[![npm version](https://img.shields.io/npm/v/@flagbridge/openfeature-provider)](https://www.npmjs.com/package/@flagbridge/openfeature-provider)
[![License](https://img.shields.io/badge/license-Apache%202.0-green)](LICENSE)

---

## Install

```bash
pnpm add @flagbridge/openfeature-provider @openfeature/server-sdk
```

`@openfeature/server-sdk` is a peer dependency and must be installed alongside this package.

---

## Usage

```ts
import { OpenFeature } from '@openfeature/server-sdk';
import { FlagBridgeProvider } from '@flagbridge/openfeature-provider';

OpenFeature.setProvider(new FlagBridgeProvider({ apiKey: 'fb_sk_eval_...' }));

const client = OpenFeature.getClient();
const value = await client.getBooleanValue('my-flag', false);
```

The provider wraps `@flagbridge/sdk-node` internally. Any configuration accepted by the Node SDK (`apiKey`, `baseUrl`, etc.) can be passed to the `FlagBridgeProvider` constructor.

---

## Supported flag types

| OpenFeature method | Supported |
|---|---|
| `getBooleanValue` | Yes |
| `getStringValue` | Yes |
| `getNumberValue` | Yes |
| `getObjectValue` | Planned |

---

## Status

This package is in early development (`0.1.x`). The OpenFeature provider interface is implemented but the full `@openfeature/server-sdk` peer integration is still in progress. The API is subject to change before `1.0.0`.

---

## Related

- [flagbridge/flagbridge](https://github.com/flagbridge/flagbridge) — Go API server (main repo)
- [flagbridge/sdk-node](https://github.com/flagbridge/sdk-node) — Node.js SDK used internally by this provider
- [OpenFeature specification](https://openfeature.dev/specification)

## License

Apache 2.0 — see [LICENSE](LICENSE) for details.
