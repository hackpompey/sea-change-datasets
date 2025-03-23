# Weather Data

## Overview

These folders contain weather data from sensors installed in port areas by [B4T](https://www.barterforthings.co.uk/case-studies/portsmouth-international-port), and an alternative dataset collected by the University of Portsmouth.

The data primarily includes temperature, humidity, pressure, rain count, and wind readings at timestamped intervals throughout 2023-2025. Coverage varies per file.

Within the [B4T folder](./B4T%20data/) are two explainers that correspond with their datasets:

- [MeteoHelix (PDF)](./B4T%20data/MeteoHelix_12July2024.pdf)
- [MeteoWind (PDF)](./B4T%20data/MeteoWind_16July2024.pdf)

Similarly, a description of the variables used in Farzad's data export can be found in the UoP data:

- [SunScout Variable Description (XLSX)](./UoP%20data/SunScout%20Variable%20Description.xlsx)

## Context

These weather data were collected to train a model for air quality prediction in port areas. The data has been combined for modelling purposes in the [combined_data_for_modelling.csv](../combined_data_for_modelling.csv) file sitting in the root directory.

## What might the data be useful for?

Besides what is stated above, the data could be used to create a weather pattern dashboard showing trends in temperature, humidity, wind and pressure. You could then break the analyses down into different time segments such as daily, seasonal and annual patterns.

By combining this data with other sets in this repo, you may be able to analyze how weather conditions affect port activity. Going further, you could build models to predict operational disruptions based on weather forecasts.
