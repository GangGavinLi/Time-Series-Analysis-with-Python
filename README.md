# Time Series Forecasting

A hands-on, notebook-based tour of time series analysis and forecasting in Python — from handling dates and time zones in pandas, through decomposition and stationarity, to ARIMA forecasting, spectral (Fourier) extrapolation, and DTW-based clustering.

Each notebook is self-contained and meant to be read and run top to bottom. Together they form a short course: the early notebooks build the data-handling foundation, the middle ones cover the classical analysis toolkit, and the last three cover forecasting and pattern discovery.

## Contents

| Notebook | What it covers |
|---|---|
| `1. Dates & Times.ipynb` | Timestamps, `DatetimeIndex`, date ranges, offsets and frequency aliases |
| `2. Time Zone Handling.ipynb` | Localizing, converting, and reasoning about tz-aware series |
| `3. Reading in data and making sensible data frames.ipynb` | Parsing fixed-width and remote data, building date indexes, `PeriodIndex` vs `DatetimeIndex`, `truncate()` |
| `4. Resampling.ipynb` | `asfreq()` vs `resample()`, upsampling/downsampling, fill strategies and aggregation |
| `5. Moving Window Functions.ipynb` | Rolling, expanding, and exponentially weighted windows; custom window functions |
| `6. Trend & Seasonality.ipynb` | Rolling-mean and regression detrending, log/power transforms, seasonal decomposition, differencing, Augmented Dickey-Fuller test |
| `7. Forecasting.ipynb` | ACF/PACF diagnostics, AR / MA / ARIMA models, back-transforming predictions to the original scale |
| `8. Spectral Analysis.ipynb` | FFT of a detrended series, selecting dominant harmonics, extrapolating the signal forward |
| `9. Clustering & Classification.ipynb` | Dynamic Time Warping distance, pairwise distance matrices, hierarchical (Ward) clustering and dendrograms |

## Data

Datasets live in `data/`:

- `AirPassengers.csv` — the classic monthly airline passenger series (trend + multiplicative seasonality), used throughout notebooks 6–8
- `50words_TEST.csv` — labeled variable-shape sequences used for the DTW clustering example
- `Earthquakes.csv` — event/interval data for additional practice

Notebook 3 also pulls the Arctic Oscillation monthly index directly from NOAA over the network, so that notebook needs an internet connection.

## Requirements

Python 3 with:

```
pandas
numpy
scipy
statsmodels
scikit-learn
matplotlib
jupyter
```

Install with:

```bash
pip install pandas numpy scipy statsmodels scikit-learn matplotlib jupyter
```

## Getting started

```bash
git clone https://github.com/GangGavinLi/Time-Series-Forecasting.git
cd Time-Series-Forecasting
jupyter notebook
```

Open the notebooks in numeric order — later ones assume the vocabulary built in the earlier ones.

## Notes

- Some notebooks use older pandas APIs (e.g. `pd.ewma`, `statsmodels.tsa.arima_model.ARIMA`). On recent versions, substitute `Series.ewm(...).mean()` and `statsmodels.tsa.arima.model.ARIMA` respectively.
- `SciPyTimeSeries.zip` contains the original packaged materials this walkthrough is built from.

## License

Add a license file if you intend others to reuse this material.
