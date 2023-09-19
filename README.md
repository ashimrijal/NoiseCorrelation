# NoiseCorrelation
=================

This notebook we implement various singnal (in particular time series) preprocessing tools. We also process seismograms using those tools, and then cross-correlate these processed signals.

As an example we try to reproduce one of the figures (in particular Fig. 1) in Shapiro et al. (2005).

1. Read Data:
We read time-series (noise) data recorded at two seismic stations from ./data directory if the number of days are less than or equals to 90 days. Otherwise, we download the data from IRIS databse.

2. Preprocess data:
To quickly demostrate some preprocessing steps we trim the time-series data to just one or a few days. You can change this to incorpoate all the adta that you've read or downloaded in the previous step. Then we detrend the data and apply bandpass filter to select the frequencies with most noice energy. Further, we perform spectral whitening on the frequency range we chose as well as time normalisation (e.g. one-bit normalisation).

3. Cross-correlation:
We then cross-correlate the processed noise signals and plot the stacked correlation between the two seismic stations. Finally, we compare the noise correlation result with an actual earthquake signal.

Reference: High-Resolution Surface-Wave Tomography from Ambient Seismic Noise, Nikolai M. Shapiro, et al. Science 307, 1615 (2005); DOI: 10.1126/science.1108339
