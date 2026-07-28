# Trainline (trainline)

Trainline plc is Europe's leading independent rail and coach ticket retailer and distribution platform, headquartered in London and listed on the London Stock Exchange, with the United Kingdom as its home market. It aggregates fares, inventory and real-time journey data from 270+ rail and coach carriers across more than 40 countries and resells that content through its own consumer app and website, through Trainline for Business, and — via Trainline Solutions / Trainline Partner Solutions — as wholesale distribution to other travel sellers through its Global API, Agent Tool and White Label products. In distribution terms Trainline is an aggregator-reseller sitting between the carriers and the traveller: rail has no GDS-equivalent oligopoly and no NDC, so Trainline is itself the intermediation layer, holding the carrier connections, the ticket-issuing accreditation and the settlement relationships that a competitor would otherwise have to rebuild carrier by carrier. Its API posture is honestly gated: the Global API is publicly described as "a modern, intuitive RESTful API" on tps.thetrainline.com but there is no developer portal, no public reference, no sandbox and no OpenAPI — access requires a commercial agreement reached through a sales conversation, and in Great Britain a retailer also needs Rail Delivery Group / Rail Settlement Plan third-party retailer accreditation and a bond. The one genuinely open artifact is the ODbL-licensed European station database Trainline publishes on GitHub, which maps its internal station ids to UIC codes, ATOC/CRS codes and carrier-specific ids.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/trainline/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/trainline/refs/heads/main/apis.yml)

## Tags

- Travel
- Rail
- United Kingdom
- Europe
- Booking
- Ticketing
- Distribution
- OTA
- Corporate Travel

## Timestamps

- **Created:** 2026-07-28
- **Modified:** 2026-07-28

## APIs

### Trainline Global API

Trainline Partner Solutions' wholesale rail and coach distribution API, sold to travel sellers, OTAs, TMCs and corporate booking tools. Trainline publicly describes it as "a modern, intuitive RESTful API built on the most up to date tech stack" covering search and browse (quoted at "600 searches per second"), booking and ticketing, payment in 10 currencies including on-account, real-time information on delays, disruption and platform changes, and aftersales — "cancellations within an hour, exchanges, changes of journey and refunds" — plus market-specific features such as UK SplitSave and seat maps, across ">44.8k stations connected". No public documentation, API reference, sandbox, machine-readable specification or self-serve signup is published; the only onboarding path is "Get in touch", with a stated average integration time of 12 weeks and Trainline-assisted carrier accreditation. No baseURL is recorded here because none is published; the host api.thetrainline.com resolves but returns HTTP 401 with a Basic auth challenge on every path and is not documented as the Global API endpoint.

- **Human URL:** [https://tps.thetrainline.com/our-products/global-api/](https://tps.thetrainline.com/our-products/global-api/)
- **Base URL:** not published

#### Tags

- Rail
- Booking
- Ticketing
- Distribution
- Travel

#### Properties

- [Documentation](https://tps.thetrainline.com/our-products/global-api/)
- [Documentation](https://www.thetrainline.com/solutions/api)
- [Support](https://tps.thetrainline.com/partner-support/)
- [Website](https://tps.thetrainline.com/)

## Common Properties

- [Domain Security](security/trainline-domain-security.yml)
- [Vulnerability Disclosure](security/trainline-vulnerability-disclosure.yml)
- [Security](https://www.thetrainline.com/terms/security)
- [Trust Center](security/trainline-trust-center.yml)
- [Compliance](https://www.thetrainline.com/terms/security)
- [Conformance](conformance/trainline-conformance.yml)
- [Well-Known](well-known/trainline-well-known.yml)
- [llms.txt](llms/trainline-llms.txt)
- [Lifecycle](lifecycle/trainline-lifecycle.yml)
- [Packages](packages/trainline-packages.yml)
- [Vocabulary](vocabulary/trainline-station-identifiers.yml)
- [JSON Schema](json-schema/trainline-station.json)
- [Website](https://www.thetrainline.com/)
- [Website](https://www.trainlinegroup.com/)
- [Portal](https://tps.thetrainline.com/)
- [Documentation](https://tps.thetrainline.com/our-products/)
- [Support](https://tps.thetrainline.com/partner-support/)
- [Terms of Service](https://www.thetrainline.com/terms)
- [Terms of Service](https://tps.thetrainline.com/terms-and-conditions/)
- [Privacy Policy](https://www.thetrainline.com/terms/privacy)
- [Blog](https://tps.thetrainline.com/blog-and-media/)
- [Blog](https://media.trainline.com/)
- [GitHub Organization](https://github.com/trainline)
- [GitHub Organization](https://github.com/trainline-eu)
- [GitHub Repository](https://github.com/trainline-eu/stations)
- [LinkedIn](https://www.linkedin.com/company/trainline)
- [Twitter](https://x.com/thetrainline)
- [Support](https://support.thetrainline.com/en/support/home)
- [Partners](https://www.thetrainline.com/about-us/partnerships)
- [Investors](https://www.trainlinegroup.com/investors)

## Enrichment (2026-07-28)

Contract discovery found **no machine-readable contract** for the Global API. `/openapi.json`,
`/openapi.yaml`, `/swagger.json`, `/v1/openapi.json` and `/api-docs` were probed on
`api.thetrainline.com` (HTTP 401 Basic challenge on every path), `tps.thetrainline.com`,
`www.thetrainline.com` and `www.trainlinegroup.com` (404). No GraphQL surface, no MCP server, no
AsyncAPI, no webhook catalogue, no Postman workspace (Postman search returns 0), no SDK in any
registry, no status page, no changelog, no sandbox. Those absences are recorded as data, not
fabricated around.

What Trainline **does** publish, and what was harvested:

| Artifact | Method | What it is |
| --- | --- | --- |
| [`llms/trainline-llms.txt`](llms/trainline-llms.txt) | searched | Real `/llms.txt` (476 KB) served at `www.thetrainline.com` — consumer-site scope |
| [`well-known/`](well-known/trainline-well-known.yml) | searched | Only live `/.well-known/` JSON on any Trainline host: OIDC discovery + JWKS for the Umbraco CMS behind `www.trainlinegroup.com` (corporate site, **not** the Global API) |
| [`security/trainline-vulnerability-disclosure.yml`](security/trainline-vulnerability-disclosure.yml) | searched | `security-external@thetrainline.com`, explicit "no payment for reporting vulnerabilities"; `hackerone.com/trainline` is an *unclaimed community page*, not a Trainline programme |
| [`security/trainline-trust-center.yml`](security/trainline-trust-center.yml) | searched | PCI DSS Level 1 (merchant *and* service provider), ISO 27001 `IS 775108`, ISO 22301 `BCMS 763415`, AWS/EEA residency, 99.9% uptime commitment |
| [`security/trainline-domain-security.yml`](security/trainline-domain-security.yml) | probed | TLS 1.3 + HSTS on the consumer and corporate hosts (TLS 1.2 on `tps.`), DNSSEC on `thetrainline.com`, DMARC `p=reject`, no CAA anywhere |
| [`conformance/trainline-conformance.yml`](conformance/trainline-conformance.yml) | searched | Every standard claimed or observable — including **no OSDM claim**, despite third parties building OSDM Places APIs on Trainline's open station data |
| [`lifecycle/trainline-lifecycle.yml`](lifecycle/trainline-lifecycle.yml) | searched | 99.9% uptime commitment, 12-week integration; no versioning policy, no deprecation policy, no status page |
| [`packages/trainline-packages.yml`](packages/trainline-packages.yml) | searched | **Zero** API client libraries in any registry; the only first-party packages are front-end/infra tooling |
| [`json-schema/trainline-station.json`](json-schema/trainline-station.json) | derived | 76-property JSON Schema for the ODbL station record, derived from the real `stations.csv` header + README |
| [`vocabulary/trainline-station-identifiers.yml`](vocabulary/trainline-station-identifiers.yml) | derived | The station-identifier crosswalk — UIC, ATOC/CRS, SNCF, DB, ÖBB, CFF, Trenitalia, NTV, Renfe, Entur, Benerail, WESTbahn, FlixBus, Distribusion, Busbud, IATA |

The finding worth keeping: Trainline's most reusable machine-readable asset is not its API, it is
the ODbL station-identifier crosswalk it gives away — 71,781 records mapping its internal ids to
every carrier's id system in European rail. The commercial contract is closed; the identity layer
underneath it is open.

## Switching Cost

Recorded in full in [review.yml](review.yml).

| Dimension | Finding |
| --- | --- |
| Interface shape | `proprietary-documented` — no OSDM, no OpenTravel, no NDC; a Trainline-specific REST contract, documented only after contract |
| Second source | `alternatives-with-migration` — SilverRail, Distribusion, Omio, Rail Europe, Amadeus/Sabre rail, or direct-to-carrier; all are re-integrations |
| Exit path | `export-on-request` — GDPR portability by email to DPO@thetrainline.com; no partner export operation published |
| Identifier portability | Station identity is open and portable (UIC, ATOC/CRS, per-carrier ids, ODbL); transaction/order identity is undisclosed |
| Contractual lock-in | Nothing published — TPS terms are a website-use policy only |
| Distribution model | `aggregator-reseller` — Trainline *is* the intermediation layer for European rail |
| NDC posture | Not applicable (not an airline); no OSDM claim published either |
| Access gate | `commercial-agreement` — sales conversation, 12-week integration, carrier accreditation |

## Maintainers

- Kin Lane — kin@apievangelist.com
