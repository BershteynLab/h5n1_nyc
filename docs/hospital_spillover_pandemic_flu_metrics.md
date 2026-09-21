# Hospital spillover metrics — `pandemic_flu`

Incidence stream: **symptomatic** · 300 simulation days.

Baselines: ward occupancy 79.8%, ICU 79.4%.

City free beds (staffed × (1 − occupancy)): ward **3227**, ICU **346**.

Peak city census: ward **2917**, ICU **316**.

Spillover volume: ward **42833** patients, ICU **5159**.

## Bed strain timing

| Metric | First day | Cum. cases that day | First stretch (days) | Total days over |
|--------|-----------|---------------------|----------------------|-----------------|
| ward_any_hospital | 5 | 9,500 | 2 | 127 |
| icu_any_hospital | 2 | 4,347 | 6 | 156 |
| ward_citywide_aggregate | — | — | 0 | 0 |
| icu_citywide_aggregate | — | — | 0 | 0 |

## Top 3 hospital systems (v1 catchment cumulative cases)

1. **NYC H+H** — 595,241 cases · 45 ZIPs
2. **NEW YORK - PRESBYTERIAN** — 281,261 cases · 25 ZIPs
3. **MOUNT SINAI HEALTH SYSTEM** — 255,289 cases · 18 ZIPs

## Top 3 hospital systems (routed ward admissions after spillover)

1. **NYC H+H** — 14,825 ward admissions
2. **NEW YORK - PRESBYTERIAN** — 10,585 ward admissions
3. **MOUNT SINAI HEALTH SYSTEM** — 6,754 ward admissions

## Most vulnerable ZIPs (high cases / low free acute beds)

| ZIP | Cum. cases | Assigned hospital | Network | Free acute | Ratio |
|-----|------------|-------------------|---------|------------|-------|
| 11230 | 29,442 | MAIMONIDES MIDWOOD COMMUNITY (1293) | MAIMONIDES HEALTH | 24 | 1216.6 |
| 10456 | 32,151 | BRONXCARE CENTER FULTON MANDY (1164) | INDEPENDENT | 29 | 1112.5 |
| 11229 | 23,689 | MAIMONIDES MIDWOOD COMMUNITY (1293) | MAIMONIDES HEALTH | 24 | 978.9 |
| 10002 | 27,858 | NYP: LOWER MANHATTAN (1437) | NEW YORK - PRESBYTERIAN | 30 | 938.0 |
| 11385 | 31,040 | WYCKOFF HEIGHTS MC (1318) | INDEPENDENT | 34 | 915.6 |
| 11355 | 31,818 | FLUSHING HOSPITAL MEDICAL CENTER (1628) | MEDISYS HEALTH NETWORK | 37 | 855.3 |
| 11226 | 34,168 | UNIVERSITY: SUNY DOWNSTATE (1320) | SUNY DOWNSTATE | 45 | 759.3 |
| 10468 | 26,436 | NYP: ALLEN HOSPITAL (3975) | NEW YORK - PRESBYTERIAN | 36 | 734.3 |
| 11233 | 22,625 | INTERFAITH MEDICAL CENTER (1309) | ONE BROOKLYN HEALTH | 32 | 696.2 |
| 11213 | 20,672 | INTERFAITH MEDICAL CENTER (1309) | ONE BROOKLYN HEALTH | 32 | 636.1 |

## Notes

- Assignment: v1 nearest hospital (EPSG:2263); spillover walks next-nearest citywide.
- Ward demand uses `ratio_hospitalization_per_case`; ICU among ward via `ratio_icu_given_hospitalization`; census = discharge vs in-hospital-death rectangular LOS mixture (ward-only vs ICU).
- Illustrative ZIP apportionment (population × post-onset healthcare burden index), not spatial transmission.
- System rankings treat DOH `INDEPENDENT` campuses as separate systems (facility name used as the system label).
