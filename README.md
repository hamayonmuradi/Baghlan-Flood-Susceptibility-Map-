# Flood Susceptibility Mapping – Baghlan Province, Afghanistan

GIS-based flood susceptibility assessment for Baghlan Province using ten flood-conditioning factors, validated against historical flood events.

![Baghlan Flood Susceptibility Map](images/baghlan_flood_susceptibility.png)

## Overview

Baghlan lies in north-eastern Afghanistan, spanning the Hindu Kush foothills and the Baghlan–Kunduz river plain. Flash and riverine floods repeatedly affect settlements and farmland along its river network. This project maps where flooding is most likely, to support land-use planning and risk reduction.

- **Study area:** Baghlan Province (14 districts)
- **Output:** Susceptibility index in four classes: Low, Moderate, High, Very High
- **Coordinate system:** WGS 1984 UTM Zone 42N
- **Tools:** [ArcGIS Pro / QGIS / Python – edit]

## Key findings

- High and Very High susceptibility concentrate along the main river corridors and the low-lying plains of the north-west (Baghlan-e-Jadid, Pul-e-Khumri), where most recorded flood events fall.
- Very High pockets appear around Khwaja Hejran and Khost Wa Fereng, where steep terrain drains into narrow valleys.
- The high-elevation, rangeland-dominated south is mostly Moderate.
- [Add: share of area in each class, e.g. "X% of the province is High or Very High"]

## Conditioning factors

| Factor | Why it matters | Source |
|---|---|---|
| Elevation | Low ground collects runoff; range 436–5,399 m | [DEM source, resolution] |
| Slope | Steep slopes speed runoff; flat areas pond water | Derived from DEM |
| Curvature | Concave areas concentrate flow | Derived from DEM |
| Topographic Wetness Index (TWI) | Tendency of water to accumulate | Derived from DEM |
| Land cover | Surface roughness and infiltration (rangeland, crops, built area, bare ground, etc.) | [Dataset, year] |
| Lithology (reclassified) | Permeability class controls infiltration | [Geological map source] |
| Average annual rainfall | Main driver of runoff volume | [Dataset, period] |
| Drainage density | Dense networks drain faster | Derived from stream network |
| Flow accumulation | Identifies concentrated flow paths | Derived from DEM |
| Distance from rivers | Proximity to channels raises exposure | Derived from stream network |

![Conditioning factors](images/conditioning_factors.png)

## Methodology

1. Prepare and clip all layers to the province boundary; resample to a common resolution ([x] m) and projection.
2. Derive terrain factors (slope, curvature, TWI, flow accumulation, drainage density) from the DEM.
3. Reclassify each factor into susceptibility classes.
4. Weight and combine the factors using **[method: AHP / frequency ratio / random forest / etc.]**.
5. Classify the final index into four classes.
6. Validate against historical flood events using **[AUC / success rate curve / etc.]**.

## Validation

[Add: number of flood points, validation metric and result.]

## Limitations

- Results depend on input data resolution and quality, especially rainfall and lithology.
- Historical flood points are limited and clustered, so validation is strongest in the north-west.
- This is a susceptibility map, not a hazard or risk map; it does not model flood depth, return period or exposure.

## Repository structure

```
├── images/          # Exported maps (PNG)
├── data/            # Small vector data (e.g. districts, flood points)
├── notebooks/       # Python / GEE scripts
├── docs/            # Methodology notes
└── README.md
```

Large rasters are not stored here; see [Zenodo / Drive link].

## Data sources

[List each dataset with link and license.]

## How to cite

Muradi, H. (2026). *Flood susceptibility mapping of Baghlan Province, Afghanistan.* GitHub. [URL]

## License

Code: MIT. Maps and documentation: CC BY 4.0.

## Author

**Hamayon Muradi** – GIS & Remote Sensing | Kabul, Afghanistan
[LinkedIn / email]
