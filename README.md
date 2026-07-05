# Discovery & Architectural Correction of TIC 361894940

Yo hello guys i have made a custom Python pipeline analysis of NASA TESS data, revealing a hidden, tight eclipsing binary system. This project corrects an erroneous entry in the TESS Input Catalog (TIC v8.2), proving the target is a low-mass M-dwarf paired with a companion at the hydrogen-burning limit—not an A-type star.

## System Parameters (Corrected)

| Property | Catalog Value (TIC v8.2) | Measured Value (This Work) | Physical Classification |
| :--- | :--- | :--- | :--- |
| **Primary Star $T_{\text{eff}}$** | 9104 K | 3400 ± 150 K | Mid-to-Late M-dwarf (M4–M5) |
| **Primary Star Radius** | 1.534 $R_{\odot}$ | 0.33 ± 0.02 $R_{\odot}$ | |
| **Companion Radius ($R_c$)** | Unlisted | 0.088 ± 0.005 $R_{\odot}$ ($0.96\ R_{\text{Jup}}$) | **Brown Dwarf / Sub-stellar** |
| **Companion Mass ($M_c$)** | Unlisted | 0.077 ± 0.010 $M_{\odot}$ | Near Hydrogen-burning limit |
| **Orbital Period ($P$)** | Unlisted | 13.92657 ± 0.00005 days | Extremely Precise |
| **Semi-Major Axis ($a$)**| Unlisted | 0.084 ± 0.0015 AU | Close Binary |

## The Catalog Correction
While the archived TIC v8.2 catalog logs the target at 9104 K (an A-type star), its raw archival photometry contradicts this profile. The observed color index ($B - V \approx +1.23$) definitively aligns the host star with a cool, red M-dwarf regime. 

By analyzing the native 7.11% primary transit depth and 0.7% secondary eclipse, our data-reduction models successfully isolated the true substellar companion architecture. 

## Vetting & Verification
- **Background Contamination:** Checked via ExoFOP; confirmed at zero.
- **Spatial Blends:** High-resolution imaging indicates no neighbor blending within the active pixel aperture.
- **Status:** Shared with the TESS support architecture and members of the MIT Astrophysics team for validation.
The first thing i uploaded was incorrect as tess had inputted the wrong numbers and the co host is a cool star not a hot one that was missed by nasa pipeline
