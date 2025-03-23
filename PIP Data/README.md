# Portsmouth International Port (PIP) Data

## Overview

The three files include the ship arrival and departure times at each linkspan/berth[^1], along with ship details.

- [pip.csv](./pip.csv) - port arrivals and departures, by ship name and date
- [ship-info.csv](./ship-info.csv) - details on each ship referenced in the pip.csv file
- [sea-change-data.xlsx](./sea-change-data.xlsx) - extended details such as origin port, next port, etc.

## Context

The data was collected by Portsmouth International Port to understand how many ships come into port, how long the ships tend to stay in port, and potentially useful information about each ship such as it's gross tonnage (GRT), length overall (LOA), etc.

## What might the data be useful for?

The data could be useful to modal ship routes, workload at ports, and other input features for modelling. Practically, the data lends itself well to visualisations and data prediction.

[^1]: A "linkspan" is a type of drawbridge connection used at ferry terminals which allows for tidal changes.
