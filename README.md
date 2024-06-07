# Solar Adoption in Amherst: Analyzing the Impact of Rent-to-Homeowner Ratio

This repository contains the code, data, and findings from a study that investigates the relationship between the rent-to-homeowner ratio (RHR) and heating energy choices, as well as solar adoption potential in Amherst, Massachusetts. The study aims to provide guidance for targeted energy transition policies that promote equitable renewable energy adoption across diverse socioeconomic blocks.

## Key Features
* Analysis of the correlation between RHR and factors such as median income, heating energy patterns, and solar feasibility
* Utilization of linear regression and random forest models to predict RHR based on census variables
* Assessment of solar suitability using parameters like roof area and sunlight exposure
* Identification of solar adoption strategies for high-rent and low-rent areas
* Introduction of RHR as a crucial factor in energy policy planning

## Data
The study utilizes the following datasets:
* `census_data.csv`: Contains information on geographic locations, residential characteristics, and block-level attributes
* `gas_meter_data.csv`: Includes detailed information about natural gas usage in homes with gas installations
* `solar_data.csv`: Comprises information about the solar potential of individual housing units

## Methodology
The study employs various data analysis techniques, including:
* Calculation of RHR and categorization of blocks into low-rent, median, and high-rent groups
* Analysis of the relationship between RHR and other census variables using correlation heatmaps and regression models
* Examination of heating energy source patterns across different rent categories
* Evaluation of solar energy adoption potential based on roof area and sunlight exposure

## Results
The findings suggest that:
* High-rent areas, despite lower median incomes, should focus on community-based solar projects
* Low-rent areas offer extensive space for large solar installations
* Targeting energy transition policies based on RHR can ensure a more equitable distribution of benefits and costs associated with decarbonizing residential heating

## Policy Implications
The study provides a strategic guide for policymakers to promote equitable solar energy adoption across different socioeconomic areas:
* Prioritize community-based solar projects in high-rent areas
* Implement a hybrid approach of individual and community solar initiatives in median-rent areas
* Offer targeted incentives and financial support for individual solar projects in low-rent areas

This repository serves as a valuable resource for researchers, policymakers, and stakeholders interested in understanding the role of RHR in shaping energy choices and promoting equitable solar adoption in diverse communities.

# Home Energy Use, Demographics, and Solar Potential data set

README

- solar_data.csv
Contains information about the solar potential of each home in the data set.
Columns:
- house_id: a unique hashed ID corresponding to a single housing unit (house or apartment)
            in the data set.
- device_id: a unique numeric IC which indexs the correct row in meter_data.csv, which 
             provides the electric usage of each housing unit in the data set.
- gas_meter_id: a unique numeric ID which indexs the correct row in gas_meter_data.csv, which 
                provides the gas usage of each housing unit in the data set.
- (lat, long): two columns providing the latitude, longitude coordinates of the housing unit.
- hours_of_sunlight_per_year: provides the number of hours of viable sunlight received by the
                              roof of this housing unit each year, as reported by Google
                              Project Sunroof.
- sq_ft_available_for_solar_panels: provides the square footage of the roof of the housing
                                    unit, as reported by Google Project Sunroof.


- meter_data.csv
Contains information about the electricity usage of each home in the data set.
Columns:
- house_id: a unique hashed ID corresponding to a single housing unit (house or apartment)
            in the data set.
- gas_meter_id: a unique numeric ID for each house in the data set with a natural gas
                installation.
- (2020-01-01 00:00:00...): multiple columns of time series data representing the electric
                            usage of this housing unit.  Each column gives the electric usage 
                            (in kWh, meaning kilowatt/hours) during a 15 minute window of 2020.


- gas_meter_data.csv
Contains information about the natural gas usage of homes in the data set which have a 
natural gas installation.
Columns:
- house_id: a unique hashed ID corresponding to a single housing unit (house or apartment)
            in the data set.
- gas_meter_id: a unique numeric ID for each house in the data set with a natural gas
                installation.
- (2020-01-01 00:00:00...): multiple columns of time series data representing the gas usage
                            of this housing unit.  Each column gives the gas usage (in CCF,
                            meaning hundred cubic feet) during one hour of 2020.


- census_data.csv
Contains information about the community in which the homes of the data set are located.
Columns:
- Block: the Census reports demographic data at a block-level granularity.  This column gives
         the ID of a single block in the community.
- Median Income: Census estimate of the median income in the given block.
- Total Population: Census estimate of the number of people in the given block.
- Employment Rate: Census estimate of the number of people employed in the given block.
- Poverty: Census estimate of the number of people living in poverty in the given block.
- Total Housing Units: Census estimate of the number of housing units (e.g. houses/apartments)
                       in the given block.
- Renter-Occupied Units: Census estimate of the number of housing units occupied by renters in
                         the given block.
- Electric Heating Units: Census estimate of the number of housing units primarily heated 
                          using electricity in this block.
- Gas Heating Units: Estimate of number of housing units primarily heated using natural gas in
                     this block.
- Oil Heating Units: Estimate of number of housing units primarily heated using heating oil in
                     this block.
- Median Year Structure Built: Census estimate of the median year in which the housing units
                               in this block were built.  The columns explained below provide
                               a more granular breakdown of each block's housing stock.
    - after2014: (estimate) housing units built after 2014.
    - 2010to2013: (estimate) housing units built between 2010 and 2013.
    - 2000to2009: (estimate) housing units built between 2000 and 2009.
    - 1990to1999: (estimate) housing units built between 1990 and 1999.
    - 1980to1989: (estimate) housing units built between 1980 and 1989.
    - 1970to1979: (estimate) housing units built between 1970 and 1979.
    - 1960to1969: (estimate) housing units built between 1960 and 1969.
    - 1950to1959: (estimate) housing units built between 1950 and 1959.
    - 1940to1949: (estimate) housing units built between 1940 and 1949.
    - pre1939: (estimate) housing units built before 1939.
- House IDs: a list of the house_ids from the data set which belong to the given block.
