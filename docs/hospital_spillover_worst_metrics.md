# Hospital spillover metrics — `worst`

Incidence stream: **symptomatic** · 300 simulation days.

Baselines: ward occupancy 79.8%, ICU 79.4%.

City free beds (staffed × (1 − occupancy)): ward **3227**, ICU **346**.

Peak city census: ward **3227**, ICU **346**.

Spillover volume: ward **30335** patients, ICU **3024**.

## Bed strain timing

| Metric | First day | Cum. cases that day | First stretch (days) | Total days over |
|--------|-----------|---------------------|----------------------|-----------------|
| ward_any_hospital | 1 | 3,166 | 105 | 110 |
| icu_any_hospital | 0 | 1,481 | 120 | 135 |
| ward_citywide_aggregate | 3 | 7,264 | 6 | 21 |
| icu_citywide_aggregate | 1 | 3,166 | 10 | 99 |

## Top 3 hospital systems (v1 catchment cumulative cases)

1. **NYC H+H** — 1,341,939 cases · 45 ZIPs
2. **NEW YORK - PRESBYTERIAN** — 634,087 cases · 25 ZIPs
3. **MOUNT SINAI HEALTH SYSTEM** — 575,535 cases · 18 ZIPs

## Top 3 hospital systems (routed ward admissions after spillover)

1. **NYC H+H** — 9,233 ward admissions
2. **NEW YORK - PRESBYTERIAN** — 6,784 ward admissions
3. **MOUNT SINAI HEALTH SYSTEM** — 4,333 ward admissions

## Most vulnerable ZIPs (high cases / low free acute beds)

| ZIP | Cum. cases | Assigned hospital | Network | Free acute | Ratio |
|-----|------------|-------------------|---------|------------|-------|
| 11230 | 66,376 | MAIMONIDES MIDWOOD COMMUNITY (1293) | MAIMONIDES HEALTH | 24 | 2742.8 |
| 10456 | 72,484 | BRONXCARE CENTER FULTON MANDY (1164) | INDEPENDENT | 29 | 2508.1 |
| 11229 | 53,405 | MAIMONIDES MIDWOOD COMMUNITY (1293) | MAIMONIDES HEALTH | 24 | 2206.8 |
| 10002 | 62,804 | NYP: LOWER MANHATTAN (1437) | NEW YORK - PRESBYTERIAN | 30 | 2114.6 |
| 11385 | 69,977 | WYCKOFF HEIGHTS MC (1318) | INDEPENDENT | 34 | 2064.2 |
| 11355 | 71,732 | FLUSHING HOSPITAL MEDICAL CENTER (1628) | MEDISYS HEALTH NETWORK | 37 | 1928.3 |
| 11226 | 77,030 | UNIVERSITY: SUNY DOWNSTATE (1320) | SUNY DOWNSTATE | 45 | 1711.8 |
| 10468 | 59,598 | NYP: ALLEN HOSPITAL (3975) | NEW YORK - PRESBYTERIAN | 36 | 1655.5 |
| 11233 | 51,007 | INTERFAITH MEDICAL CENTER (1309) | ONE BROOKLYN HEALTH | 32 | 1569.5 |
| 11213 | 46,604 | INTERFAITH MEDICAL CENTER (1309) | ONE BROOKLYN HEALTH | 32 | 1434.0 |

## Notes

- Assignment: v1 nearest hospital (EPSG:2263); spillover walks next-nearest citywide.
- Ward demand uses `ratio_hospitalization_per_case`; ICU among ward via `ratio_icu_given_hospitalization`; census = discharge vs in-hospital-death rectangular LOS mixture (ward-only vs ICU).
- Illustrative ZIP apportionment (population × post-onset healthcare burden index), not spatial transmission.
- System rankings treat DOH `INDEPENDENT` campuses as separate systems (facility name used as the system label).
