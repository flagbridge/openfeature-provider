# FlagBridge OpenFeature Provider

Official [OpenFeature](https://openfeature.dev/) provider for [FlagBridge](https://github.com/flagbridge/flagbridge).

> **Note:** Active development happens in the [monorepo](https://github.com/flagbridge/flagbridge/tree/main/packages/openfeature-provider). This repo is used for distribution and issue tracking.

## Installation

```bash
npm install @flagbridge/openfeature-provider @openfeature/server-sdk
# or
pnpm add @flagbridge/openfeature-provider @openfeature/server-sdk
```

## Quick Start

```typescript
import { OpenFeature } from '@openfeature/server-sdk';
import { FlagBridgeProvider } from '@flagbridge/openfeature-provider';

OpenFeature.setProvider(new FlagBridgeProvider({ apiKey: 'your-api-key' }));

const client = OpenFeature.getClient();
const enabled = await client.getBooleanValue('new-feature', false);
```

## Documentation

Full docs at [flagbridge.io/docs/sdk/openfeature](https://flagbridge.io/docs/sdk/openfeature)

## License

Apache 2.0
