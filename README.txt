Home Energy Use, Demographics, and Solar Potential data set
===========================================================
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