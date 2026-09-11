# Pulse-shaping-and-the-Nyquist-criterion


This repository contains a Python simulation comparing rectangular, sinc, raised-cosine (RC), and root-raised-cosine (RRC) pulses to study the Nyquist zero-ISI criterion and the bandwidth–timing trade-off governed by the roll-off factor[cite: 2, 4]. 

## Features
* **Filter Generation:** Custom implementation of discrete filters from closed-form mathematical equations, utilizing L’Hôpital’s rule to resolve $0/0$ singularities at $t=0$, $t=\pm T/2\alpha$, and $t=\pm T/4\alpha$ without relying on library filter-design functions[cite: 2, 4].
* **Transmission Chain:** Simulates an upsampled BPSK symbol impulse train at 16 samples per symbol[cite: 4].
* **Matched Filtering:** Validates that cascading a non-Nyquist transmit RRC filter with a receive RRC filter perfectly restores the RC response and zero-crossings at symbol intervals[cite: 2, 4].
* **Bandwidth Analysis:** Computes absolute bandwidth, 99% energy containment, and $-3$ dB bandwidth limits across roll-off factors ($\alpha = 0.0, 0.25, 0.5, 1.0$)[cite: 4].
* **Jitter & ISI Tolerance:** Evaluates worst-case intersymbol interference (ISI) and generates 400-symbol eye diagrams to prove that higher bandwidth directly correlates with increased timing margin before eye closure[cite: 4].

## Dependencies
* Python 3[cite: 2]
* NumPy[cite: 4]
* Matplotlib[cite: 4]

## Usage
The script is designed to run out-of-the-box in Google Colab (`Runtime → Run all`) or any local Jupyter/Python 3 environment[cite: 4].

To run locally:
1. Clone the repository.
2. Install the required libraries: `pip install numpy matplotlib`
3. Execute the script: `python experiment7_colab_2.py`

### Saving Outputs
By default, the script simply displays the six Matplotlib figures[cite: 4]. To export the data, change the `SAVE` variable to `True` at the top of the script[cite: 4]. This will write all graphs as high-resolution PNGs and output the raw numerical matrices to `validation_tables.txt` in your working directory[cite: 4].
