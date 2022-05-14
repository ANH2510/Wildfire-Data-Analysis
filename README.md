# Wildfire-Data-Analysis

#### Language: 
- Python

The project analyzes wildfire in Lai Chau - a state of Vietnam - a South East Asia Country. Lai Chau, where wildfires normally occur during dry weather, in addition to complicated climate changes, a large accumulation of combusible materials. (40 km x 40 km)

The analyzed area is 40x40 km and timespan is from January 2019 to December 2019. The period of time should include at least 3-5 year to make the stronger conclusion but because the dataset is considerably heavy to load into the system, therefore one year period was used to analyze. 

Two Hypotheses are proposed to test in the project: 
- 1. The wildfire in Vietnam occur often in dry season (from March to August) yearly
- 2. Most of wildfire cases in Vietnam happen in small scale which are under well control and do not last long

#### Souce: 
 - [Climate Data Store](https://cds.climate.copernicus.eu/)

API request: 

import cdsapi

c = cdsapi.Client()

c.retrieve(
    'satellite-fire-burned-area',
    {
        'format': 'zip',
        'origin': 'esa_cci',
        'sensor': 'modis',
        'variable': 'pixel_variables',
        'version': '5_1_1cds',
        'region': 'asia',
        'year': '2019',
        'month': [
            '01', '02', '03',
            '04', '05', '06',
            '07', '08', '09',
            '10', '11', '12',
        ],
        'nominal_day': '01',
    },
    'download.zip')



