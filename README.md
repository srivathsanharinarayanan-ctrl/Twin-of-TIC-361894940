# Twin-of-TIC-361894940 # The Twin of TIC 361894940: Discovery of a Hidden Stellar Companion 

Hi all! This repository contains a custom Python data-processing pipeline to ingest, clean and analyze raw space telescope telemetry from NASA's Transiting Exoplanet Survey Satellite (TESS). 

By applying automated light curve normalization and phase-folding algorithms, this pipeline successfully revealed a previously undocumented **M-dwarf companion star** orbiting the bright, hot primary star **TIC 361894940**.

---

## The Discovery & Science

When looking at raw TESS data, lightcurves are very damn noisy but my pipeline has flattened the noise and i have used an ML figure out the candidate
### 1. The specifications of the host star-
Cross-referencing the TESS Input Catalog (TIC) and ExoFOP stellar parameters, the primary star is identified as a massive **A-type main-sequence star**:
* **Effective Temperature:** 9104 K 
* **Radius:** 1.534 Solar Radii

### 2. The Twin  (The Companion)
My pipeline phase-folded the light curve data over a precise **13.92657-day orbital period**, isolating two critical significant things-
* **Primary Transit Depth:** A deep flux drop of **71.106 ppt** (~7.11%) when the companion passes directly in front of the primary star. Which indicates it's not a planet but it's a small star.
* **Secondary Eclipse:** A clear secondary drop at the exact phase boundaries, confirming a highly luminous secondary body rather than a planet.

Using the transit depth equation, the radius of the companion was extracted:

The companion star's radius is found by taking the square root of the flux drop (0.071106) and multiplying it by the primary star's radius (1.534 Solar Radii), which yields approximately **0.41 Solar Radii**.

A companion radius of **0.41 Solar Radii** perfectly matches the physical evolutionary profile of an **M-dwarf star** (Red Dwarf) or in simpler terms a cood red dwarf which is good! 

---

## Vetting & False-Positive Elimination

To ensure the signal was genuine and not an instrumental artifact or background blend, the system was vetted against global archival catalogs:
* **Zero Contamination:** The ExoFOP TESS pipeline calculates a background contamination ratio of "none."
* **No Spatial Blends:** High-resolution spatial imaging records confirm there are ZERO nearby neighbor stars within the TESS pixel aperture. 
* **Native Signal:** Because there is no contamination, the 7.11% transit signal is mathematically proven to belong natively to this specific tight binary system.

---

## Pipeline Features
* **Light Curve Ingestion:** Automatically downloads and parses SPOC/QLP light curves from the MAST archive.
* **Flattening & Detrending:** Removes long-term stellar variability and spacecraft systematics using custom filtering.
* **Phase-Folding Engine:** Folds the time-series data over calculated periods to stack transit events and maximize the signal-to-noise ratio.
* **Geometric Modeling:** Extracts exact transit depths for both primary and secondary eclipses.

---

## License
This project is licensed under the **MIT License**
