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
