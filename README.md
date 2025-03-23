# Hack Pompey x Sea Change Dataset

> **Introduction from the Portsmouth International Port**
>
> Portsmouth International Port (PIP) is rather different to other United Kingdom ports in the fact that it is one of the very few large economically viable municipal ports left in the country. A municipal port is a port owned by the local authority, and this means that the owners of the port are the people of Portsmouth. This allows the port management to do things that other ports avoid. We measure our emissions and we take responsibility for those emissions insofar as we are spending a lot of time, trouble and money attempting to reduce those emissions.
>
> However, **‘you cannot manage what you do not measure’** is a very apt saying when it comes to emissions and air quality.
>
> We have our own air quality monitors up and measuring, and we have new ships coming in (Brittany Ferries) that not only offer the opportunity of truly zero emission shipping but also zero or near zero particulate emissions when burning LNG alongside.
>
> What is missing is the ability to make that information available in a format that people will recognize and be able to use. <strong>People do not want to know the part per million of a particular pollutant, they want to know if air quality is going to be good or bad!</strong>
>
> This is where this hackathon comes in...

## Project Ideas

### Pip Challenge 1: Air Quality Prediction

**Objective**

Create an application that predicts and visualizes real-time air quality conditions for the Portsmouth area by integrating multiple environmental and traffic data sources. Your solution should have an intuitive interface to display current and forecasted air quality information.

**Data sources**

- You can use the data in [this repository](#dataset-contents) to build a predictive model, or to simulate real time data.
- Use factors such as wind direction, ships incoming, peak commuter time, wind speed (pollutants do not diffuse) and meteorological conditions (High or Low Pressure affects dispersal of pollutants) to build a model of air quality.
- Real-time Air Quality data is available via API from https://aqicn.org/data-platform/api/H3204/
- Real-time AIS data (ships coming and going) is available via API from https://api.myshiptracking.com

### PIP Challenge 2: Estimate Carbon Emissions from Ships Entering the Solent

**Objective**

Create the first assessment of carbon emissions produced by shipping entering the Solent for Portsmouth, Southampton and western points, using an intentionally conservative approach.

**Data sources**

- You’ll use AIS (Automatic Identification System) data[^1] for ships passing into the Solent from the Nab Tower
- This data tracks ship movements in the area
- Some data may be useful in this repository, however you may find https://marinetraffic.com (and https://api.myshiptracking.com in particular) more helpful

**Simplified Approach**

1. Make a conservative estimate of fuel consumption for all vessels
2. Calculate the resulting carbon emissions

**Fuel Consumption Assumptions**

- Instead of using actual consumption rates, which vary widely, I.e:
  - Reefer container ships (refrigerated cargo): ~48 tonnes of fuel per day
  - Large ships going into Southampton: up to several hundred tonnes per day
  - Smaller coastal ships: as little as 8 tonnes per day
- Use a _simplified_ rate of 1 tonne of diesel per hour for _all_ ships
  - This is intentionally lower than actual consumption
  - Makes the final carbon estimate defensible as a minimum baseline

**Journey Time Assumptions**

- Portsmouth: 1 hour travel time in/out
- Southampton: 3 hours travel time in/out

**Calculation Steps**:

1. Multiply the hourly consumption (1 tonne/hour) by each ship's journey time
2. Use [government conversion tables](https://view.officeapps.live.com/op/view.aspx?src=https://assets.publishing.service.gov.uk/media/6722566a3758e4604742aa1e/ghg-conversion-factors-2024-condensed_set__for_most_users__v1_1.xlsx&wdOrigin=BROWSELINK) to calculate carbon emissions from the fuel used
3. Sum up the results to get total carbon emissions

## Other Project Ideas

<em>

For most of these projects you may wish to use data from this repo, or live AIS data available from https://marinetraffic.com (API available at: https://api.myshiptracking.com).

</em>

**Ship Emissions Tracker**  
Visualize real-time carbon footprints of vessels entering the solent.

**Maritime Traffic Optimizer**  
Create an algorithm to reduce port congestion and waiting times for ships.

**Ship Happens**  
A racing game where players navigate vessels through the Solent while managing fuel consumption and avoiding emissions alerts.

**Virtual Harbour Tour**  
Visualisation/tour that identifies and provides information about ships currently in port.

**Catch of the Day**  
App connecting consumers with fishing vessels to purchase sustainably caught local seafood.

**Name My Ship**  
Silly AI tool that suggests ship names based on cargo, destination and weather conditions.

**Tide Times Plus**  
Notification system or app for suggesting optimal harbour entry times based on time, traffic and berth availability.

**Battleships: Solent**  
The Battleships game, but using real AIS data.

**Portsmouth Harbour Bingo**  
Web or mobile game where players check off different types of vessels spotted entering the harbour.

## Dataset Contents

[Linkspan Info](/Linkspan%20Info/README.md)<br>
Activity reports from linkspans (berths) at the Portsmouth International Port broken down by type of ship data: total Gross Register Tonnage, Length Overall, Enginer Power and Ship Speed.

[Portsmouth International Port (PIP) Data](./PIP%20Data/README.md)<br>
Ship routes, workload at ports, and input features that could be used for modelling such as gross tonnage (GRT), length overall (LOA), etc.

[Weather Data](/Weather%20Data/README.md)<br>
Temperature, humidity, pressure, rain count and wind readings at timestamped intervals throughout 2023-2025 at port locations provided by B4T and the University of Portsmouth.

[CO<sub>2</sub> Data](/CO2%20data/README.md)<br>
CO<sub>2</sub>, NO<sub>x</sub> and SO<sub>2</sub> readings taken at regular intervals throughout 2023-2025 provided by B4T.

[Combined Data for Modelling (CSV)](./combined_data_for_modelling.csv)<br>
The complete dataset that has been used to develop a machine learning model for CO<sub>2</sub> prediction. Created by pulling together information from all the other datasets. Note that while the legwork has been done to combine the data for modelling purposes here, there is still utility in the source materials themselves for your own goals.

<hr>

**Please note**  
This dataset has been made publicly available for the purposes of the "Hack Pompey x Sea Change" hackathon taking place on the 29th March 2024. Public access will be removed shortly after the hackathon is finished.

<small>

The data in this repository is licensed under the terms of the [CC BY-NC 4.0 license](https://creativecommons.org/licenses/by-nc/4.0/). See the included [LICENSE.txt](/LICENSE.txt) file for details.

</small>

[^1]: Live AIS data can be viewed here: https://marinetraffic.com. The same data is made available via API here: https://api.myshiptracking.com
