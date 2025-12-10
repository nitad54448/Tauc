# UV-Vis Tauc Plotter & Bandgap Estimator

A lightweight, single-file web application for analyzing UV-Vis spectroscopic data and estimating optical bandgaps ($E_g$) using the Tauc method. 

Built with **JavaScript** and **Plotly**, this tool runs entirely in your web browser with no installation required. It supports both standard Absorbance/Transmittance data and Diffuse Reflectance (Kubelka-Munk) analysis.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Platform](https://img.shields.io/badge/platform-Web-orange.svg)

## Features

* **Zero Installation:** Runs from a single HTML file. No Python, MATLAB, or server setup required.
* **Privacy Focused:** All data processing happens client-side in your browser. Your data is never uploaded to a server.
* **Smart Import:**
    * Supports `.csv`, `.txt`, and `.dat` files.
    * Auto-detects delimiter (comma, tab, space).
    * Smart-guesses units (Wavelength vs. Energy) and Data Type (Absorbance, Transmittance, Reflectance).
* **Advanced Analysis:**
    * **Direct Bandgap:** Plots $(\alpha h\nu)^2$ vs Energy.
    * **Indirect Bandgap:** Plots $(\alpha h\nu)^{1/2}$ vs Energy.
    * **Kubelka-Munk (F(R)):** Automatic conversion for Diffuse Reflectance data.
    * **Thickness Correction:** Calculates absorption coefficient ($\alpha$) based on sample thickness.
* **Interactive Fitting:**
    * Real-time calculation of $E_g$ (x-intercept), Slope, and $R^2$.
* **Reporting:**
    * **PDF Report:** Generates a timestamped report with all plots and results.
    * **CSV Export:** Downloads the full processed dataset (Energy, $\alpha$, Tauc Y-values) and calculation summaries.

##  How to Use

1.  **Download:** Get the `index.html` file from this repository.
2.  **Open:** Double-click `index.html` to open it in any modern web browser (Chrome, Edge, Firefox, Safari).
3.  **Load Data:** Click the **"Browse"** button and select your UV-Vis data file(s).
4.  **Analyze:**
    * The app will attempt to guess your parameters.
    * Select the correct **Y-Axis Type** (Absorbance, Transmittance, or Reflectance).
    * Click **"Smart Auto-Detect Range"** to find the bandgap region automatically.
    * Adjust the **Min/Max eV** manually if needed to perfect the fit (look for the red dotted line).
5.  **Export:** Use the buttons at the bottom left to download a CSV of your data or a PDF report.

##  Theoretical Background

The application implements the **Tauc relation**:

$$(\alpha h\nu)^{1/n} = A(h\nu - E_g)$$

Where:
* $\alpha$ is the absorption coefficient.
* $h\nu$ is the photon energy (eV).
* $E_g$ is the optical bandgap.
* $n$ denotes the nature of the transition:
    * $n = 1/2$ for **Direct** allowed transitions.
    * $n = 2$ for **Indirect** allowed transitions.

### Calculation Modes

#### 1. Transmission / Absorbance
For transparent thin films or liquids:
$$\alpha = \frac{2.303 \times A}{d}$$
*Where $A$ is Absorbance and $d$ is sample thickness (cm).*

If Transmittance (%T) is provided:
$$A = 2 - \log_{10}(\%T)$$

#### 2. Diffuse Reflectance (Kubelka-Munk)
For opaque powders or films, the **Kubelka-Munk function** $F(R)$ is used as a proportional proxy for $\alpha$:
$$F(R) = \frac{(1 - R)^2}{2R}$$
*Where $R$ is the normalized reflectance ($0 < R < 1$).*

## 🛠 Dependencies

This project uses the following open-source libraries (loaded via CDN):

* [Bootstrap 5](https://getbootstrap.com/) - UI & Layout.
* [Plotly.js](https://plotly.com/javascript/) - Interactive Graphing.
* [PapaParse](https://www.papaparse.com/) - CSV/Text file parsing.
* [jsPDF](https://github.com/parallax/jsPDF) - PDF Generation.
* [html2canvas](https://html2canvas.hertzen.com/) - Canvas rendering for PDF.



---
*Created for fast, easy, and reproducible optical bandgap analysis.*