# Blink Charging (blink)

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

Blink Charging Co. (Nasdaq: BLNK) operates the Blink Network of Level 2 and DC Fast electric vehicle chargers across North America and Europe, alongside brands acquired via SemaConnect, Blue Corner, BlueLA, and Envoy. Blink's charger hardware (Series 7/8/9) is OCPP 2.0.1 certified for CSMS interoperability, and in September 2025 Blink joined Hubject's Intercharge eRoaming platform as a charge point operator using the OCPI protocol so third-party e-mobility service providers can route drivers and billing to Blink stations. Blink also runs a gated BlinkMap API developer program (station locations, hours, and live network status) and a Blink Fleet platform that partners such as Presto and BetterFleet integrate with via API for fleet charging, sessions, and billing.

**Access model:** None of Blink's programs currently publish a full public self-serve API reference. The BlinkMap API requires signing up directly with Blink for an API key, technical documentation, and email support. The Blink Fleet API is accessed through Blink's partner program (as used by Presto and BetterFleet), not open signup. The OCPI roaming interface is a B2B integration brokered through Hubject rather than a Blink-hosted public endpoint. This entry documents the real, named programs and standards Blink participates in, honestly modeling endpoint shapes only where a sourced historical reference exists (the BlinkMap API), and describing the Fleet and OCPI surfaces at the product/program level without fabricating unconfirmed technical details.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/blink/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/blink/refs/heads/main/apis.yml)

## Tags

- EV Charging
- Electric Vehicle
- Charging Stations
- OCPI
- OCPP
- Fleet Management
- Roaming
- DC Fast Charging

## Timestamps

- **Created:** 2026-07-03
- **Modified:** 2026-07-03

## Industry Standards

- **OCPP 2.0.1** — Blink's Series 7/8/9 charger hardware is certified against Open Charge Point Protocol 2.0.1, a device-to-backend (charger-to-CSMS) control protocol authored by the Open Charge Alliance. OCPP runs over WebSocket, but it is a hardware interoperability standard rather than a Blink-published developer API.
- **OCPI** — Since September 2025, Blink is a charge point operator (CPO) on Hubject's Intercharge eRoaming platform, using the Open Charge Point Interface protocol (REST/HTTPS) for standardized session roaming and billing/CDR exchange with e-mobility service providers (eMSPs) across the US, Canada, and Mexico.

## APIs

### Blink Charging Locations & Status API

Gated third-party integrator program (marketed as the BlinkMap API) returning Blink-compatible charging station locations, hours of operation, and live network status - station map pins reflect Available / Charging / Unavailable states. Signing up with Blink provides an API key plus technical reference and email support; a public self-serve API reference is not currently published. The endpoint shapes modeled here (geo-radius Locations search, name-based Search, and per-location Status lookup) come from a historical official Blink "API Map" PDF (dated January 2014) referenced by a long-standing third-party Ruby client library; current field names and paths are not independently re-verified against Blink's present-day version and should be confirmed with Blink directly before integration.

- **Human URL:** [https://prod.blinknetwork.com/developer.html](https://prod.blinknetwork.com/developer.html)
- **Base URL:** `https://api.blinknetwork.com/map/v1`

#### Tags

- Charging Stations
- Locations
- Status
- BlinkMap

#### Properties

- [Documentation](https://prod.blinknetwork.com/developer.html)
- [OpenAPI](openapi/blink-charging-locations-status-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)


#### Tags

- Fleet
- Sessions
- Billing
- Reservations
- Partner Integration

#### Properties

- [Press Release (Presto)](https://blinkcharging.com/news/blink-and-presto-announce-strategic-collaboration-to-provide-advanced-tools-for-ev-fleet-charging)
- [Press Release (BetterFleet)](https://theevreport.com/blink-charging-partners-with-betterfleet-for-fleet-management)


#### Tags

- OCPI
- Roaming
- eMSP
- Hubject
- Intercharge

#### Properties

- [Press Release](https://blinkcharging.com/news/hubject-teams-with-blink-charging-to-further-expand-intercharge-network-across-north-america)
- [Documentation (Hubject)](https://www.hubject.com/blog-posts/hubject-teams-with-blink-charging-to-further-expand-intercharge-network-across-north-america)

## Pricing

Blink does not publish pricing for any of its developer/partner API programs (BlinkMap, Fleet, OCPI) - access to each is negotiated directly with Blink or its roaming/fleet partners. Driver-facing charging session pricing (unrelated to API access) is set per station by the site host and billed per kWh where regulations allow or per minute otherwise, varying by charger power level (Level 2 vs. DC Fast) and membership tier; there is no published flat national rate.

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/blinkcharging)
- [Website](https://blinkcharging.com)
- [GitHub Organization](https://github.com/blinkcharging)
- [Documentation](https://prod.blinknetwork.com/developer.html)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
