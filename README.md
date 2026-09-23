# PrimaryCareClinicFinder
PrimaryCareClinicFinder is an R-based workflow for developing and validating a regional database of primary care clinic locations in British Columbia, Canada.

The workflow combines physician registry data, geocoding, spatial data integration, deterministic classification, and large language model (LLM)-assisted classification to identify and characterize community-based primary care clinic locations.

The final dataset includes:

- Clinic index
- Clinic name
- Clinic type
- Number of physicians
- Address
- Latitude
- Longitude
- Community Health Service Area (CHSA) name
- CHSA identifier

## Authors:
Amrit Tiwana<sup>1,2</sup>, Rita K. McCracken<sup>1</sup>

## Author affiliations:
1. Stephens Family School of Medicine, Simon Fraser University, 13450 – 102 Avenue, Surrey, BC, V3T 0A3, Canada

2. School of Community and Regional Planning, University of British Columbia, 433 – 6333 Memorial Road, Vancouver, BC, V6T 1Z2, Canada 

## Requirements 

R version 4.3.1 or higher 

## R Packages

- ggplot2
- dplyr
- sf
- ellmer

## Data Sources

The workflow integrates information from multiple data sources:
- Physician registry data
- A list of long-term care home locations
- A list of hospital locations
- A list of walk-in medical clinic locations
- A list of urgent and primary care centre (UPCC) locations
- A list of correctional facility locations

## Workflow

The analysis consists of six main steps:

1. Preprocess physician registry data

    1_preprocessing_registry_data.R

   Cleans and prepares physician registry data for subsequent analysis, including extracting and standardizing practice location information.

3. Geocode practice addresses

   2_geocoding_addresses.R

  Converts practice addresses into geographic coordinates (latitude and longitude) and prepares the locations for spatial analysis.

3. Calculate the number of physicians per location

  3_calculating_num_physicians.R

  Identifies unique practice locations and calculates the number of physicians associated with each location.

4. Spatially join facility information

  4_spatial_joining_facilities.R

  Integrates external facility datasets with physician practice locations using geographic information to identify locations corresponding to hospitals, long-term care homes, walk-in clinics, UPCCs, and correctional facilities.

5. Deterministic facility classification

  5_deterministic_classification.R

  Applies predefined rules to classify practice locations using available registry and facility information. Locations that can be confidently identified using deterministic rules are classified before LLM-assisted classification.

6. LLM-assisted classification

  6_llm_classification.R

  Uses a large language model to classify remaining unknown practice locations into predefined facility types. The model considers information such as the practice address, physician title, department, number of             physicians, and publicly available contextual knowledge.

  LLM classifications include a confidence level and rationale to support subsequent manual validation.
