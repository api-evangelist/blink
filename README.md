# Blink Charging (blink)

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
