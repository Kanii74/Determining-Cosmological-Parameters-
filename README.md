# Determining Cosmological Parameters using Type Ia Supernova Data

This repository contains the analysis performed for a **Cosmology assignment at the Indian Institute of Space Science and Technology (IIST)** under **Dr. Jagadheep**.

The objective of this project is to estimate important **cosmological parameters of the Universe** using observational data from **Type Ia supernovae**. The analysis was carried out using **Python and Jupyter Notebook**, where theoretical cosmological models were fitted to observational data to determine parameters describing the expansion of the Universe.

---

# Scientific Background

Type Ia supernovae are extremely luminous stellar explosions that occur in binary systems containing a **white dwarf star**. When the white dwarf accretes enough mass to approach the **Chandrasekhar limit (~1.44 M☉)**, runaway thermonuclear fusion is triggered and the star explodes as a supernova.

Because Type Ia supernovae reach nearly the same **peak luminosity**, they serve as **standard candles**. This allows astronomers to determine distances to galaxies across cosmological scales.

The distance to a supernova is determined using the **distance modulus relation**

$$
\mu = m - M
$$

where

- **m** — apparent magnitude  
- **M** — absolute magnitude  

From this relation we obtain the **luminosity distance**. When combined with the **redshift (z)** of the host galaxy, it provides information about the **expansion history of the Universe**.

This relationship forms the **Supernova Hubble Diagram**, which allows us to estimate key cosmological parameters such as:

- **Ωₘ** — matter density parameter  
- **ΩΛ** — dark energy density parameter  
- **H₀** — Hubble constant  

---

# Objective

The objectives of this assignment were:

1. Use observational **Type Ia supernova data**  
2. Plot the **distance modulus vs redshift relation**  
3. Fit theoretical **cosmological models** to the observational data  
4. Estimate the **cosmological parameters of the Universe**

The parameters were obtained by performing **curve fitting between theoretical cosmological models and observational measurements**.

---

# Dataset

The dataset used in this analysis is:

```
SCP_sn1a_data (2).txt
```

This dataset contains observational measurements of **Type Ia supernovae from the Union2 dataset**.

Each row contains:

| Column | Description |
|------|-------------|
| Redshift (z) | Cosmological redshift of the supernova |
| Distance Modulus (m − M) | Difference between apparent and absolute magnitude |
| Error | Measurement uncertainty |

---

# Repository Structure

```
Determining-Cosmological-Parameters
│
├── Cosmology Assignment - 2.ipynb
│   Main Jupyter notebook containing the analysis code
│
├── Cosmology Assignment - 2 code.pdf
│   PDF version of the code used in the analysis
│
├── Cosmology Assignment - 2.pdf
│   Report describing the methodology and results
│
├── SCP_sn1a_data (2).txt
│   Observational Type Ia supernova dataset
│
└── README.md
    Project documentation
```

---

# Methodology

The analysis was implemented in **Python** using the following scientific libraries:

- **NumPy**
- **SciPy**
- **Astropy**
- **Matplotlib**

---

## Data Import

The supernova dataset was imported using `astropy.io.ascii`, and the following columns were extracted:

- redshift  
- distance modulus  
- measurement error  

---

## Cosmological Models

Two cosmological models were considered.

### Flat Universe (Matter + Λ)

For a **flat universe**, the density parameters satisfy

$$
\Omega_m + \Omega_\Lambda = 1
$$

The luminosity distance was calculated using the cosmological distance integral and converted into the **distance modulus**.

---

### Curved Universe (Matter + Dark Energy)

A more general cosmological model including curvature was implemented using the **ΛCDM cosmology model provided by the Astropy library**.

---

## Curve Fitting

The cosmological parameters were estimated using

```
scipy.optimize.curve_fit
```

This method determines the best-fit parameters by minimizing the difference between the **observational data** and the **theoretical cosmological model**.

---

# Plots Generated

The notebook generates several plots during the analysis.

### Distance Modulus vs Redshift

- Scatter plot of observational data  
- Error bars included for measurement uncertainties  

### Log-Scale Redshift Plot

- Distance modulus plotted against redshift using a **logarithmic redshift axis**

### Cosmological Model Fits

Two fitted cosmological models are shown:

- **Flat Universe (Matter + Λ)**  
- **Curved Universe (Matter + Dark Energy)**  

These plots illustrate how well the theoretical models reproduce the **observed supernova data**.

---

# Results

The cosmological parameters obtained from the fits are:

## Flat Universe (Matter + Λ)

| Parameter | Value |
|----------|------|
| Ωₘ | 0.287 ± 0.019 |
| ΩΛ | 0.713 ± 0.019 |
| H₀ | 69.986 ± 0.003 km s⁻¹ Mpc⁻¹ |

---

## Curved Universe (Matter + Dark Energy)

| Parameter | Value |
|----------|------|
| Ωₘ | 0.268 ± 0.069 |
| Ω_DE | 0.679 ± 0.116 |
| H₀ | 69.907 ± 0.004 km s⁻¹ Mpc⁻¹ |

These values are consistent with modern cosmological measurements indicating that the Universe is dominated by **dark energy and dark matter**.

---

# Conclusion

This project demonstrates how **observational Type Ia supernova data can be used to determine cosmological parameters**.

By constructing the **distance modulus–redshift relation** and fitting theoretical cosmological models to the observational data, we can estimate parameters that describe the **expansion history of the Universe**.

The results obtained in this analysis are consistent with the **ΛCDM cosmological model**, which is currently the standard model of cosmology.
