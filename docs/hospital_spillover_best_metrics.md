# Hospital spillover metrics — `best`

Incidence stream: **symptomatic** · 300 simulation days.

Baselines: ward occupancy 79.8%, ICU 79.4%.

City free beds (staffed × (1 − occupancy)): ward **3227**, ICU **346**.

Peak city census: ward **693**, ICU **136**.

Spillover volume: ward **0** patients, ICU **173**.

## Bed strain timing

| Metric | First day | Cum. cases that day | First stretch (days) | Total days over |
|--------|-----------|---------------------|----------------------|-----------------|
| ward_any_hospital | — | — | 0 | 0 |
| icu_any_hospital | — | — | 0 | 0 |
| ward_citywide_aggregate | — | — | 0 | 0 |
| icu_citywide_aggregate | — | — | 0 | 0 |

## Top 3 hospital systems (v1 catchment cumulative cases)

1. **NYC H+H** — 191,608 cases · 45 ZIPs
2. **NEW YORK - PRESBYTERIAN** — 90,538 cases · 25 ZIPs
3. **MOUNT SINAI HEALTH SYSTEM** — 82,177 cases · 18 ZIPs

## Top 3 hospital systems (routed ward admissions after spillover)

1. **NYC H+H** — 2,667 ward admissions
2. **NEW YORK - PRESBYTERIAN** — 1,260 ward admissions
3. **MOUNT SINAI HEALTH SYSTEM** — 1,144 ward admissions

## Most vulnerable ZIPs (high cases / low free acute beds)

| ZIP | Cum. cases | Assigned hospital | Network | Free acute | Ratio |
|-----|------------|-------------------|---------|------------|-------|
| 11230 | 9,477 | MAIMONIDES MIDWOOD COMMUNITY (1293) | MAIMONIDES HEALTH | 24 | 391.6 |
| 10456 | 10,350 | BRONXCARE CENTER FULTON MANDY (1164) | INDEPENDENT | 29 | 358.1 |
| 11229 | 7,625 | MAIMONIDES MIDWOOD COMMUNITY (1293) | MAIMONIDES HEALTH | 24 | 315.1 |
| 10002 | 8,967 | NYP: LOWER MANHATTAN (1437) | NEW YORK - PRESBYTERIAN | 30 | 301.9 |
| 11385 | 9,992 | WYCKOFF HEIGHTS MC (1318) | INDEPENDENT | 34 | 294.7 |
| 11355 | 10,242 | FLUSHING HOSPITAL MEDICAL CENTER (1628) | MEDISYS HEALTH NETWORK | 37 | 275.3 |
| 11226 | 10,999 | UNIVERSITY: SUNY DOWNSTATE (1320) | SUNY DOWNSTATE | 45 | 244.4 |
| 10468 | 8,510 | NYP: ALLEN HOSPITAL (3975) | NEW YORK - PRESBYTERIAN | 36 | 236.4 |
| 11233 | 7,283 | INTERFAITH MEDICAL CENTER (1309) | ONE BROOKLYN HEALTH | 32 | 224.1 |
| 11213 | 6,654 | INTERFAITH MEDICAL CENTER (1309) | ONE BROOKLYN HEALTH | 32 | 204.7 |

## Notes

- Assignment: v1 nearest hospital (EPSG:2263); spillover walks next-nearest citywide.
- Ward demand uses `ratio_hospitalization_per_case`; ICU among ward via `ratio_icu_given_hospitalization`; census = discharge vs in-hospital-death rectangular LOS mixture (ward-only vs ICU).
- Illustrative ZIP apportionment (population × post-onset healthcare burden index), not spatial transmission.
- System rankings treat DOH `INDEPENDENT` campuses as separate systems (facility name used as the system label).
