# Envelop

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
