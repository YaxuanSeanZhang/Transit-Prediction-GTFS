# Transit-Transfer-Stop

## Overview
This repo develops a pipeline to infer and visualize individuals' transfer stops by utlizing information from both transit onboard data and the General Transit Feed Specification (GTFS) data. The analysis process considers transit schedule information (e.g., date and hour), trip direction, and a minimum distance rule. The output consists of a prediction table and an interactive visualization of the trip route.

## Data
* [**Transit-Onboard**](https://gisdata.mn.gov/dataset/us-mn-state-metc-society-tbi-transit-onboard2016): This dataset includes origin-destination records for transit trips across all regional routes and providers.
* [**General Transit Feed Specification (GTFS)**](https://gisdata.mn.gov/dataset/us-mn-state-metc-trans-transit-schedule-google-fd): GTFS data encompass bus, light rail, and commuter rail service details for the Minneapolis / St. Paul metropolitan area. The data consists of multiple tables, such as routes, trips, stops, stop_times, shape, and more.
  
## Files
The repository contains several essential files:
* `Onboard_Processing.ipny`: This notebook reads and preprocesses transit onboard data, with a focus on extracting route and transfer information.
* `Merge_GTFS.ipny`: This notebook reads the GTFS data and performs data merging operations across various tables to obtain comprehensive transit information.
* `Individual_Possible_Trip.ipny`: This notebook spatially and temporally infers an individual's transfer stop, considering factors such as route, time, and distance.
* `Visualization.ipny`: This notebook interactively visualizes the predicted trip route.

## Limitation
* The project primarily focuses on individuals who make only one transfer before reaching their current boarding route.
* The code visualizes the trip from origin to the boarding stop, rather than the entire trip.
* Due to performance considerations, the provided demo only contains data for only 10 people's trips.
