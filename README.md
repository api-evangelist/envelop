# Envelop

Envelop is the missing GraphQL plugin system, maintained by The Guild. It wraps the entire GraphQL execution pipeline — `parse`, `validate`, `execute`, and `subscribe` — with composable lifecycle hooks, enabling developers to build and share plugins for authentication, caching, tracing, error handling, rate limiting, and more.

- **Website:** https://the-guild.dev/graphql/envelop
- **Documentation:** https://the-guild.dev/graphql/envelop/docs
- **Plugin Hub:** https://the-guild.dev/graphql/envelop/plugins
- **GitHub:** https://github.com/graphql-hive/envelop
- **LinkedIn:** https://www.linkedin.com/company/the-guild-software
- **npm:** https://www.npmjs.com/package/@envelop/core

## About

Envelop is schema-agnostic and HTTP-server agnostic. It integrates with any GraphQL server framework (GraphQL Yoga, Apollo Server, Express, Fastify, etc.) and any schema-first or code-first GraphQL schema. The core plugin API is based on hooks triggered before and after each phase of GraphQL execution, giving plugin authors precise control over the pipeline.

## Key Capabilities

- **Authentication** — `@envelop/generic-auth` for generic auth patterns
- **Caching** — `@envelop/parser-cache`, `@envelop/validation-cache`
- **Error handling** — `useErrorHandler`, `useMaskedErrors`
- **Tracing** — `@envelop/sentry`, `@envelop/opentelemetry`
- **Rate limiting** — `@envelop/rate-limiter`, `useResourceLimitations`
- **Analytics** — `@envelop/hive`, `@envelop/statsd`
- **Federation** — `@envelop/apollo-federation`

## Quick Start

```bash
npm i @envelop/core graphql
```

```javascript
import * as GraphQLJS from 'graphql'
import { envelop, useEngine, useSchema } from '@envelop/core'

const getEnveloped = envelop({
  plugins: [useEngine(GraphQLJS), useSchema(mySchema)]
})
```

## Repository Structure

```
envelop/
  apis.yml                          # API Evangelist catalog entry
  README.md                         # This file
  plans/
    envelop-plans.md                # Licensing and plan information
  rate-limits/
    envelop-rate-limits.md          # Rate limiting notes
  finops/
    envelop-finops.md               # Cost and FinOps guidance
```

## Maintainer

Kin Lane — kin@apievangelist.com
