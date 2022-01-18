# Wildlife GPS data processing

### This repository contains an R markdown output file of the GPS Processing script for cleaning and filtering wildlife GPS data. Detailed below are the steps this script walks you through, starting with raw GPS (animal collar data in this case) and resulting with filtered and separated by season/year data.

1. Read in all individual .csv files in a folder and combine them
1. Filter the combined .csv and set proj4string to the UTM zone the data is from
1. Filter to remove any N/A data, any erroneous altitude data (set this a priori), and filter by your date range of interest
1. Create a date time variable, add it to your dataset, and ensure it is in the proper format
1. Generate spatial boundaries based on a priori assumptions/locations and filter your data using these boundaries
1. Calculate the number of GPS points per individual
1. Calculate step length to determine distance and time between successive GPS points - this also allows you to calculate a movement rate that we will use later!
1. Check for movement rates that exceed a certain value and then filter out any movement rates above that value (e.g., it may be the case that your animals can not move greater than 15 kilometres in an hour, so you can remove any data points that exceed 15km/hr).
1. Filter by season and year for any downstream annual/seasonal analyses
