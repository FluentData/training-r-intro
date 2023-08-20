The following datasets are available to use in examples and exercises in the course:

# chicago_air.csv

This data set contains air quality measurements from Chicago in 2021. The measurements were taken daily and there are 365 records from
January 1, 2021 to December 31, 2021.

## Dataset Fields

1. `date`: The date of the observations in the format YYYY-MM-DD.
2. `ozone`: The ozone concentration, in parts per million (ppm).
3. `temp`: The temperature on that day, in degrees Fahrenheit.
4. `pressure`: The atmospheric pressure on that day, in millibars (mb).
5. `month`: The month of the observation, represented as an integer (1 for January, 2 for February, etc.).
6. `weekday`: The day of the week, represented as an integer (1 for Monday, 2 for Tuesday, etc.).

## Summary Statistics

|       |     ozone |    temp |   pressure | 
|:------|----------:|--------:|-----------:|
| count |     363   |    365  |      365   |
| mean  |   0.0367  |   63.53 |   1004.35  |
| std   |   0.0102  |   19.19 |      5.79  |
| min   |   0.012   |   13    |    984.9   |
| 25%   |   0.029   |   49    |   1000.5   |
| 50%   |   0.036   |   66    |   1003.8   |
| 75%   |   0.043   |   81    |   1007.8   |
| max   |   0.065   |   93    |   1023.1   |

--- 

# chicago_daily.csv

This data set contains air quality measurements from Chicago in 2021. The measurements were taken daily.

## Dataset Fields

1. `date`: The date of the observations in the format YYYY-MM-DD.
2. `no2`: The concentration of nitrogen dioxide, in parts per billion (ppb).
3. `pm25`: The concentration of particulate matter with a diameter of 2.5 micrometers or smaller, in micrograms per cubic meter (µg/m³).
4. `so2`: The concentration of sulfur dioxide, in parts per billion (ppb).

## Summary Statistics

|       |      no2 |     pm25 |       so2 |
|:------|---------:|---------:|----------:|
| count | 329      | 317      | 363       |
| mean  |  28.7337 |  18.3164 |   2.65262 |
| std   |  12.6662 |  16.887  |   1.74934 |
| min   |   6.5    |   1.2    |   0       |
| 25%   |  18.8    |   9.5    |   1.5     |
| 50%   |  27.5    |  14.8    |   2.4     |
| 75%   |  36.7    |  21.3    |   3.2     |
| max   |  69.1    | 182.3    |  11.9     |

---

# chicago_wind.csv

This data set contains wind and ozone measurements from Chicago in 2021. The measurements were taken hourly.

## Dataset Fields

1. `datetime`: The date and time of the observations in the format YYYY-MM-DD HH:mm:ss.
2. `wind_speed`: The wind speed, in miles per hour (mph).
3. `wind_direction`: The wind direction, in degrees from true north.
4. `ozone`: The ozone concentration, in parts per million (ppm).

## Summary Statistics

|       |   wind_speed |   wind_direction |        ozone |
|:------|-------------:|-----------------:|-------------:|
| count |   4834       |        4834      | 4739         |
| mean  |      4.10559 |         186.766  |    0.0300749 |
| std   |      2.49251 |          95.6862 |    0.0158709 |
| min   |      0.1     |           0      |    0         |
| 25%   |      2.2     |         105      |    0.019     |
| 50%   |      3.8     |         205      |    0.029     |
| 75%   |      5.7     |         261      |    0.039     |
| max   |     17.5     |         360      |    0.091     |

---

# chicago_aqs.csv

This dataset represents air quality measurements taken at various sites in the Chicago area. The measurements include various air quality parameters, such as pollutant concentrations, Air Quality Index (AQI), and other related information. The dataset is structured in a "long" format, where each row represents a single observation for a specific parameter at a particular site, date, and time.

## Dataset Fields

1. `State_Code`
2. `County_Code`
3. `Site_Number`
4. `Parameter_Code`
5. `POC`
6. `Latitude`
7. `Longitude`
8. `Datum`
9. `Parameter_Name`
10. `Duration_Description`
11. `Pollutant_Standard`
12. `Date_Local`
13. `Year`
14. `Day_In_Year_Local`
15. `Units_of_Measure`
16. `Exceptional_Data_Type`
17. `Observation_Count`
18. `Observation_Percent`
19. `Arithmetic_Mean`
20. `First_Maximum_Value`
21. `First_Maximum_Hour`
22. `AQI`
23. `Daily_Criteria_Indicator`
24. `State_Name`
25. `County_Name`
26. `City_Name`
27. `Local_Site_Name`
28. `Address`
29. `MSA_or_CBSA_Name`
30. `Data_Source`

## Summary Statistics

| Location (Latitude, Longitude, State, County, City, Local Site) | Pollutant | Arithmetic_Mean_count | Arithmetic_Mean_mean | Arithmetic_Mean_std | Arithmetic_Mean_min | Arithmetic_Mean_25% | Arithmetic_Mean_50% | Arithmetic_Mean_75% | Arithmetic_Mean_max | First_Maximum_Value_count | First_Maximum_Value_mean | First_Maximum_Value_std | First_Maximum_Value_min | First_Maximum_Value_25% | First_Maximum_Value_50% | First_Maximum_Value_75% | First_Maximum_Value_max |
|:--------------------------------------------------------------:|:---------:|:---------------------:|:--------------------:|:-------------------:|:-------------------:|:-------------------:|:-------------------:|:-------------------:|:-------------------:|:-------------------------:|:------------------------:|:-----------------------:|:-----------------------:|:-----------------------:|:-----------------------:|:-----------------------:|:-----------------------:|
| (41.7514, -87.713488, Illinois, Cook, Chicago, COM ED MAINTENANCE BLDG) | Sulfur dioxide | 363 | 1.59937 | 0.801869 | -0.079167 | 0.84375 | 1.81667 | 2.24375 | 3.72083 | 363 | 2.65262 | 1.74934 | 0 | 1.5 | 2.4 | 3.2 | 11.9 |
| (41.855243, -87.75247, Illinois, Cook, Cicero, COOK COUNTY TRAILER) | Nitrogen dioxide (NO2) | 329 | 14.7969 | 6.86124 | 4.1375 | 9.7375 | 13.9182 | 18.0167 | 40.8375 | 329 | 28.7337 | 12.6662 | 6.5 | 18.8 | 27.5 | 36.7 | 69.1 |
| (41.864426, -87.748902, Illinois, Cook, Cicero, LIBERTY SCHOOL) | PM2.5 Raw Data | 317 | 7.31678 | 5.65392 | -1.53809 | 3.725 | 6.59583 | 9.68333 | 32.6708 | 317 | 18.3164 | 16.887 | 1.2 | 9.5 | 14.8 | 21.3 | 182.3 |

