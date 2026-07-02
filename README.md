# Antarctic Sea-ice Extent Anomalies Impact Interannual Variability of Phytoplankton Chlorophyll-*a* in Southern Ocean Frontal Zones

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)

## Overview

This repository contains code and analysis for examining the relationship between Antarctic sea ice variability and phytoplankton productivity (measured as chlorophyll-*a* concentration) across different oceanographic frontal zones in the Southern Ocean. The analysis covers the period 1998-2024 and is designed for a manuscript submitted to *Geophysical Research Letters* (GRL).

## Research Questions

1. How has Antarctic sea ice extent changed over the past 26 years (1998-2024)?
2. Are there spatial patterns in sea ice concentration trends across the Southern Ocean?
3. How does chlorophyll-*a* concentration respond to sea ice variability in different frontal zones?
4. What is the optimal temporal lag structure for sea ice-chlorophyll relationships?
5. How do chlorophyll-*a* concentrations differ across distinct sea ice regimes?

## Repository Structure

```
sea_ice_code/
├── Figure_1.ipynb              # Study area map with frontal zones and climatology
├── Figure_2.ipynb              # Sea ice trends (spatial and temporal)
├── Figure_3_and_4.ipynb        # Sea ice-chlorophyll relationships
├── Figure_5.ipynb              # Sea ice regime analysis
├── Supplementary.ipynb         # Temporal lag structure testing
├── README.md                   # This file
└── requirements.txt            # Python package dependencies (recommended)
```

## Figures Generated

### Main Manuscript Figures

- **Figure 1**: Antarctic study area showing oceanographic frontal zones (Polar Front, SACCF, Southern Boundary), climatological chlorophyll-*a* distribution, and maximum sea ice extent
- **Figure 2**: Sea ice concentration trends with spatial maps (February and September) and time series analysis using Sen's slope estimator
- **Figure 3**: Time series of chlorophyll-*a* anomalies and 1-year lagged sea ice extent anomalies across three frontal zones
- **Figure 4**: Scatter plot correlations between sea ice extent and chlorophyll-*a* anomalies showing regional differences
- **Figure 5**: Sea ice regime classification and mean chlorophyll-*a* response by regime (Low Ice, Normal Ice, High Ice)

### Supplementary Figures

- **Supplementary Figure S1**: Winter ice (Jun-Sep) to summer chlorophyll (Nov-Mar) lag analysis
- **Supplementary Figure S2**: Annual 1-year lag time series analysis

## Data Sources

**All datasets used in this study are publicly available:**

### 1. Chlorophyll-*a* Data
- **Copernicus Marine Environment Monitoring Service (CMEMS)**
  - Product: Daily, non-interpolated Level-3 Mapped global ocean colour data
  - Spatial resolution: 4 × 4 km
  - Sensors: SeaWiFS, MODIS-Aqua, MERIS, VIIRS, OLCI (merged product)
  - Temporal coverage: 1998-2023
  - DOI: https://doi.org/10.48670/moi-00280
  - Access: [Copernicus Marine Service](https://data.marine.copernicus.eu/)

### 2. Sea Ice Data
- **National Snow and Ice Data Center (NSIDC)**
  - Product: Sea Ice Concentration (SIC) and Sea Ice Extent (SIE)
  - Climate Data Record (CDR)
  - Spatial resolution: 25 km polar stereographic grid
  - Projection: EPSG:3412 (NSIDC South Polar Stereographic)
  - Temporal coverage: 1998-2024
  - DOI: https://doi.org/10.5067/MPYG15WAA4WX
  - Access: [NSIDC](https://nsidc.org/data/nsidc-0051)

### 3. Oceanographic Fronts
- **Satellite Altimetry-Derived Front Positions**
  - Fronts: Polar Front (PF), Southern Antarctic Circumpolar Current Front (SACCF), Southern Boundary (SB)
  - Based on Park et al. (2019)
  - DOI: https://doi.org/10.17882/59800
  - Access: [SEANOE](https://www.seanoe.org/data/00486/59800/)

### 4. Processed Data
- **Anomaly datasets** (SIEA and chlorophyll-*a* anomalies) are included as supplementary data files with the manuscript submission
- All processed datasets and analysis scripts will be archived in **Zenodo** with a DOI upon manuscript acceptance

## Methods Summary

### Sea Ice Analysis
- **Anomaly calculation**: Deviation from monthly climatological mean (1998-2024)
- **Trend estimation**: Sen's slope (Theil-Sen estimator) - robust to outliers
- **Regime classification**: Based on standardized anomalies (±0.5σ thresholds)

### Chlorophyll-*a* Analysis
- **Spatial aggregation**: Three frontal zones
  - PF-SACCF (Polar Front to Southern ACC Front)
  - SACCF-SB (Southern ACC Front to Southern Boundary)
  - SB-AntCoastline (Southern Boundary to Antarctic coastline)
- **Anomaly calculation**: Deviation from monthly climatological mean

## Installation and Requirements

### Python Environment
```bash
# Create a virtual environment (recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install required packages
pip install -r requirements.txt
```

### Required Packages
- Python 3.9+
- jupyter
- numpy >= 1.23
- pandas >= 1.5
- matplotlib >= 3.6
- cartopy >= 0.21
- xarray >= 2022.11
- scipy >= 1.9
- geopandas >= 0.12
- statsmodels >= 0.13
- seaborn >= 0.12

## Usage

### Running the Notebooks

1. **Start Jupyter Notebook:**
   ```bash
   jupyter notebook
   ```

2. **Run notebooks in order:**
   - Start with `Figure_1.ipynb` for study area context
   - `Figure_2.ipynb` for sea ice trends
   - `Figure_3_and_4.ipynb` for relationships
   - `Figure_5.ipynb` for regime analysis
   - `Supplementary.ipynb` for additional lag testing

3. **Each notebook is self-contained** with:
   - Data loading
   - Analysis code
   - Figure generation
   - Results interpretation

## Output Files

All figures are saved as high-resolution PNG files (300 DPI) suitable for publication:
- `Figure_1.png` - Study area map
- `Figure_2.png` - Sea ice trends
- `Figure_3.png` - Time series relationships
- `Figure_4.png` - Scatter correlations
- `Figure_5.png` - Regime analysis
- `Supplementary_FigureS1.png` - Winter-summer lag
- `Supplementary_FigureS2.png` - Annual lag

## Citation

If you use this code or data, please cite:

```
Golder, MR & Antoine, D. (2026). Antarctic Sea-ice Extent Anomalies Impact Interannual Variability of Phytoplankton Chlorophyll-a in Southern Ocean Frontal Zones. Geophysical Research Letters. 
[DOI to be added upon publication]
```

### Data Availability

- **GitHub Repository**: <https://github.com/ronygolderku/sea_ice_GRL>
- **Zenodo Archive**: DOI will be provided upon manuscript acceptance
- **Processed Anomaly Data**: Included as supplementary data files with manuscript submission

### Data Sources
- **NSIDC** (2024). Sea Ice Concentration and Extent. https://doi.org/10.5067/MPYG15WAA4WX
- **Copernicus Marine Service** (2024). Global Ocean Colour (GlobColour). https://doi.org/10.48670/moi-00280
- **Park et al.** (2019). Antarctic Circumpolar Current fronts. https://doi.org/10.17882/59800

## License

This code is released under the MIT License. See `LICENSE` file for details.

## Contributing

This repository is primarily for manuscript reproducibility. For questions or suggestions:
- Open an issue on GitHub
- Contact: [Md Rony Golder, mdrony.golder@postgrad.curtin.edu.au]

## Acknowledgments

- **Data providers**: NSIDC, Copernicus Marine Service, NASA Ocean Color
- **Computing resources**: [Your institution/computing facility]
- **Funding**: [Grant information if applicable]

---

**Last updated**: July 2, 2026

For questions about this analysis, please contact the corresponding author or open an issue on GitHub.
