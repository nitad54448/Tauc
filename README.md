uv vis Tauc plots



\# UV-Vis Tauc Plotter \& Bandgap Estimator



A lightweight, single-file web application for analyzing UV-Vis spectroscopic data and estimating optical bandgaps ($E\_g$) using the Tauc method. 



Built with \*\*JavaScript\*\* and \*\*Plotly\*\*, this tool runs entirely in your web browser with no installation required. It supports both standard Absorbance/Transmittance data and Diffuse Reflectance (Kubelka-Munk) analysis.





\## 🚀 Features



\* \*\*Zero Installation:\*\* Runs from a single HTML file. No Python, MATLAB, or server setup required.

\* \*\*Privacy Focused:\*\* All data processing happens client-side in your browser. Your data is never uploaded to a server.

\* \*\*Smart Import:\*\*

&nbsp;   \* Supports `.csv`, `.txt`, and `.dat` files.

&nbsp;   \* Auto-detects delimiter (comma, tab, space).

&nbsp;   \* Smart-guesses units (Wavelength vs. Energy) and Data Type (Absorbance, Transmittance, Reflectance).

\* \*\*Advanced Analysis:\*\*

&nbsp;   \* \*\*Direct Bandgap:\*\* Plots $(\\alpha h\\nu)^2$ vs Energy.

&nbsp;   \* \*\*Indirect Bandgap:\*\* Plots $(\\alpha h\\nu)^{1/2}$ vs Energy.

&nbsp;   \* \*\*Kubelka-Munk (F(R)):\*\* Automatic conversion for Diffuse Reflectance data.

&nbsp;   \* \*\*Thickness Correction:\*\* Calculates absorption coefficient ($\\alpha$) based on sample thickness.

\* \*\*Interactive Fitting:\*\*

&nbsp;   \* \*\*Smart Auto-Suggest:\*\* Uses a derivative-based algorithm to automatically find the linear region of the absorption edge.

&nbsp;   \* Manual fine-tuning of the linear fit range.

&nbsp;   \* Real-time calculation of $E\_g$ (x-intercept), Slope, and $R^2$.

\* \*\*Reporting:\*\*

&nbsp;   \* \*\*PDF Report:\*\* Generates a timestamped report with all plots and results.

&nbsp;   \* \*\*CSV Export:\*\* Downloads the full processed dataset (Energy, $\\alpha$, Tauc Y-values) and calculation summaries.



\##  How to Use



1\.  \*\*Download:\*\* Get the `index.html` file from this repository or look for the file at nitad54448.github.io

2\.  \*\*Open:\*\* Double-click `index.html` to open it in any modern web browser (Chrome, Edge, Firefox, Safari).

3\.  \*\*Load Data:\*\* Click the \*\*"Browse"\*\* button and select your UV-Vis data file(s).

4\.  \*\*Analyze:\*\*

&nbsp;   \* The app will attempt to guess your parameters.

&nbsp;   \* Select the correct \*\*Y-Axis Type\*\* (Absorbance, Transmittance, or Reflectance).

&nbsp;   \* Click \*\*"Smart Auto-Detect Range"\*\* to find the bandgap region automatically.

&nbsp;   \* Adjust the \*\*Min/Max eV\*\* manually if needed to perfect the fit (look for the red dotted line).

5\.  \*\*Export:\*\* Use the buttons at the bottom left to download a CSV of your data or a PDF report.



\##  Theoretical Background



The application implements the \*\*Tauc relation\*\*:



$$(\\alpha h\\nu)^{1/n} = A(h\\nu - E\_g)$$



Where:

\* $\\alpha$ is the absorption coefficient.

\* $h\\nu$ is the photon energy (eV).

\* $E\_g$ is the optical bandgap.

\* $n$ denotes the nature of the transition:

&nbsp;   \* $n = 1/2$ for \*\*Direct\*\* allowed transitions.

&nbsp;   \* $n = 2$ for \*\*Indirect\*\* allowed transitions.



\### Calculation Modes



\#### 1. Transmission / Absorbance

For transparent thin films or liquids:

$$\\alpha = \\frac{2.303 \\times A}{d}$$

\*Where $A$ is Absorbance and $d$ is sample thickness (cm).\*



If Transmittance (%T) is provided:

$$A = 2 - \\log\_{10}(\\%T)$$



\#### 2. Diffuse Reflectance (Kubelka-Munk)

For opaque powders or films, the \*\*Kubelka-Munk function\*\* $F(R)$ is used as a proportional proxy for $\\alpha$:

$$F(R) = \\frac{(1 - R)^2}{2R}$$

\*Where $R$ is the normalized reflectance ($0 < R < 1$).\*



\## 🛠 Dependencies



This project uses the following open-source libraries (loaded via CDN):



\* \[Bootstrap 5](https://getbootstrap.com/) - UI \& Layout.

\* \[Plotly.js](https://plotly.com/javascript/) - Interactive Graphing.

\* \[PapaParse](https://www.papaparse.com/) - CSV/Text file parsing.

\* \[jsPDF](https://github.com/parallax/jsPDF) - PDF Generation.

\* \[html2canvas](https://html2canvas.hertzen.com/) - Canvas rendering for PDF.



---

\*Created for fast optical bandgap analysis.\*

