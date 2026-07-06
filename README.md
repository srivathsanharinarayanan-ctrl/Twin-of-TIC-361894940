# TIC 361894940: TESS Transient Analysis Pipeline

**Discovery & Verification of AT 2024eme — A Periodic Optical Transient in TESS Data**

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Status](https://img.shields.io/badge/Status-Active-brightgreen.svg)](#)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](#)

---

## Overview

This project presents a complete analysis pipeline for detecting and verifying transient objects in TESS photometry. Initial analysis of TIC 361894940 revealed periodic variability in the TESS light curve. Through rigorous cross-validation with independent ZTF data, we identified the source as **AT 2024eme**, an optical transient with 28.691-day periodic behavior, rather than a stable eclipsing binary system.

This work demonstrates essential best practices in time-domain astronomy: rigorous verification, aperture contamination checks, and independent data cross-referencing.

---

## Quick Summary

| Property | Value | Notes |
|----------|-------|-------|
| **Target** | TIC 361894940 | TESS Input Catalog ID |
| **Initial Signal** | 7.11% periodic depth | TESS light curve |
| **Initial Period** | 13.92657 days | BLS detection |
| **Verified Identity** | AT 2024eme (Optical Transient) | ZTF cross-reference |
| **True Period** | 28.691 days | ZTF periodogram S/N = 9.192 |
| **Type** | Variable/Transient Star | Not an eclipsing binary |

---

## Discovery Process

### Phase 1: TESS Analysis

Using a custom Python pipeline, we analyzed TESS photometry for TIC 361894940:

- **Light curve extraction:** SPOC/QLP processed data, 1237 cadences
- **Periodicity search:** Box-Least-Squares (BLS) algorithm
- **Period detection:** P = 13.92657 ± 0.00005 days
- **Eclipse depth:** 7.11% primary, 0.7% secondary
- **Initial hypothesis:** M-dwarf + brown dwarf eclipsing binary

### Phase 2: Verification with ZTF

To validate the discovery, we cross-referenced with ZTF (Zwicky Transient Facility) data using the SNAD database:

**Key findings:**
- ✅ ZTF detects real periodic variability at the target location
- ✅ Periodogram shows clear signal (S/N = 9.192)
- ❌ ZTF period = 28.691 days (NOT 13.92657 days)
- ❌ Target identified as **AT 2024eme** (Optical Transient 2024)

### Phase 3: Correction & Analysis

The discrepancy between TESS and ZTF periods led to a critical discovery:

**Root cause analysis:**
- TESS detected 13.92657-day signal (likely an alias or harmonic)
- ZTF independently confirms 28.691-day fundamental period
- Ratio: 28.691 / 13.92657 ≈ 2.06 (close to 2:1 alias)
- Target is a **transient optical object**, not a stable eclipsing binary

**Physical interpretation:**
- AT 2024eme likely represents a stellar transient event (nova, supernova, or outburst)
- Periodic variability (28.7 days) may indicate rotation, pulsation, or binary orbital modulation
- Not the M+BD binary initially hypothesized

---



| Source | Period (days) | S/N | Detection Type |
|--------|---------------|-----|----------------|
| TESS BLS | 13.92657 | — | Primary frequency |
| ZTF Periodogram | 28.691 | 9.192 | Fundamental period |
| Period Ratio | 2.06 | — | ~2:1 harmonic/alias |

**Conclusion:** TESS detected a harmonic or alias of the true 28.691-day period. ZTF's independent confirmation identifies the fundamental frequency.

### Target Classification

**AT 2024eme** (Optical Transient 2024):
- **Type:** ot (optical transient)
- **Identification:** MJD 60383.0, 19'20.6" Astro-COLIBRI
- **Coordinates:** RA 296.5538°, Dec +23.6440°
- **Magnitude (average):** zg 18.65, zr 17.28, zi 16.61
- **Periodicity:** 28.691 days

**Physical nature:** Likely a stellar transient event (nova candidate, supernova, or outburst star) with periodic modulation. Further spectroscopic follow-up needed to determine exact class.

---

## Scientific Lessons Learned

### 1. Verification is Non-Negotiable

Initial TESS analysis suggested an M-dwarf + brown dwarf eclipsing binary — scientifically interesting but incorrect. Independent ZTF cross-reference revealed the true nature.

**Key takeaway:** Always verify with independent data before claiming discovery.

### 2. Period Aliases Are Real

TESS detected 13.92657 days; ZTF confirmed 28.691 days. The ratio ≈ 2:1 suggests harmonic or aliasing.

**Why this happens:**
- Sampling artifacts
- Beating between periodicities
- Observational cadence effects
- Unresolved binary/multi-periodic systems

**Solution:** Cross-reference with high-resolution, independent surveys.

### 3. Aperture Contamination in TESS

TESS pixels span ~21 arcseconds. A 17th magnitude star only ~1.5 pixels away can contaminate measurements of fainter targets.

**Best practices:**
- Always check high-resolution imaging
- Calculate flux contribution estimates
- Use ExoFOP contamination reports
- Cross-validate apertures with independent data

### 4. Transients Masquerade as Binaries

Periodic variability ≠ eclipsing binary. Other sources include:
- Rotating variables (spots, magnetic activity)
- Pulsating stars (δ Scuti, RR Lyrae)
- Transient outbursts with periodic structure
- Instrumental/systematic effects

**Lesson:** Physical interpretation requires spectroscopy, color indices, and follow-up observations.

---

## Files & Data

### Data Sources

- **TESS:** MIT Data Archive (https://archive.stsci.edu/tess/)
- **ZTF:** SNAD Database (https://ztf.snad.space/)
- **Gaia:** Gaia DR3 (https://gea.esac.esa.int/archive/)
- **PanSTARRS:** Pan-STARRS DR2 (https://panstarrs.stsci.edu/)

### Output Files

All results stored in `results/`:
- `folded_lightcurve.csv` — Phase-folded light curve data
- `periodogram_comparison.csv` — TESS vs ZTF period comparison
- `aperture_analysis.csv` — Contamination analysis results
- `analysis_summary.txt` — Final parameters & uncertainties

---

## Follow-Up Observations

To determine the true nature of AT 2024eme, we recommend:

### 1. Optical Spectroscopy (Priority: HIGH)
- Resolve emission/absorption lines
- Determine spectral type and temperature
- Identify transient classification (nova, SN Ia, etc.)
- **Instruments:** GEMINI, Keck, VLT

### 2. Extended Photometry (Priority: MEDIUM)
- Monitor 28.691-day periodicity over multiple cycles
- Check for period evolution (transient decay?)
- Cross-validate with ATLAS, ASAS-SN surveys

### 3. Infrared Observations (Priority: MEDIUM)
- 2MASS, Spitzer, or WISE
- Constrain dust content (extinction)
- Detect cool companion if present

### 4. Radial Velocity (Priority: LOW)
- If binary, measure mass function
- Confirm orbital parameters

---

## Contributors

- **Srivathsan H.N** — Analysis, discovery, verification
- **Prof. Saul Rappaport (MIT)** — Scientific review, methodology guidance

---

## Acknowledgments

- **TESS Mission** — MIT, Smithsonian Astrophysical Observatory, NASA
- **ZTF/SNAD** — Caltech, Carnegie Institution, UC Berkeley
- **Gaia Mission** — ESA
- **Pan-STARRS** — University of Hawaii, MPIA

---

## References

- Kovács, G., Zucker, S., & Mazeh, T. (2002). A Box-fitting Algorithm in the Period Search. *A&A*, 391(2), 369-377.
- Lightkurve Collaboration (2018). Lightkurve: Kepler and TESS time series analysis in Python. https://docs.lightkurve.org/
- TESS Documentation. https://tess.mit.edu/
- ZTF Public Data Release. https://www.ztf.caltech.edu/

---

## License

MIT License — See LICENSE file for details.

---

## Citation

If you use this analysis or pipeline in your research, please cite:

```bibtex
@software{srivathsan2026tic361894940,
  author = {Srivathsan, H.N.},
  title = {TIC 361894940: TESS Transient Analysis Pipeline},
  year = {2026},
  url = {https://github.com/srivathsanharinarayanan-ctrl/M-Dwarf-Brown-Dwarf-Twin-Binaries},
  note = {Discovery and verification of AT 2024eme using TESS and ZTF cross-validation}
}
```

---

## Issues & Questions

For questions, issues, or collaboration:
- **GitHub Issues:** [Open an issue](https://github.com/srivathsanharinarayanan-ctrl/M-Dwarf-Brown-Dwarf-Twin-Binaries/issues)
- **Email:** srivathsan.harinarayanan@[school].edu

---

**Status:** Analysis complete | Verification successful |  Follow-up observations recommended |  Results published on GitHub

**Last Updated:** July 5, 2026
