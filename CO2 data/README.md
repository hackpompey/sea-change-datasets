# CO<sub>2</sub> Data

## Overview

These folders contain air quality data measured by sensors installed by [B4T](https://www.barterforthings.co.uk/case-studies/portsmouth-international-port) at port locations.

The measurements include CO<sub>2</sub>, NO<sub>x</sub> and SO<sub>2</sub>, taken at regular intervals throughout 2023-2025. Coverage varies per file.

## Context

Air quality data was measured to use as ground truth for CO<sub>2</sub> air quality predictions. The sensors are installed at five locations at the port, and are set to record continuously. Data is collected via a digital link provided by B4T.

Each folder contains a PDF with guidance on the data collected.

## What might the data be useful for?

By combining this data with other sets in this repo, it may be possible to correlate emission spikes with ship arrivals, departures and docking times. From there, you could identify which types of vessels or activities contribute most to pollution.

Furthermore, the levels recorded in the dataset could be compared to international regulatory thresholds to create (or simulate) periods of alert where levels have approached or surpassed legal limits.

It may be possible to build a tool that simulates how various emission reduction strategies might affect overall air quality, using the data to create "what-if" scenarios.
