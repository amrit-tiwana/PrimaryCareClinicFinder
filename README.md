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

# Authors:
Amrit Tiwana<sup>1,2</sup>, Rita K. McCracken<sup>1</sup>

# Author affiliations:
1. Stephens Family School of Medicine, Simon Fraser University, 13450 – 102 Avenue, Surrey, BC, V3T 0A3, Canada

2. School of Community and Regional Planning, University of British Columbia, 433 – 6333 Memorial Road, Vancouver, BC, V6T 1Z2, Canada 

# Requirements 

R version 4.3.1 or higher 

## Packages

- ggplot2
- dplyr
- sf
- ellmer

# Materials

## Data Sources

The workflow integrates information from multiple data sources:
- Physician registry data
- A list of long-term care home locations
- A list of hospital locations
- A list of walk-in medical clinic locations
- A list of urgent and primary care centre locations
- A list of correctional facility locations

## Code

- 1_preprocessing_registry_data.R
- 2_geocoding_addresses.R
- 3_calculating_num_physicians.R
- 4_spatial_joining_facilities.R
- 5_deterministic_classification.R
- 6_llm_calssification.R

## Steps 

