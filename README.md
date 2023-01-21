# Mapping-Cities-API
 
Please note to enter your own openweathermap key and google key in api_keys.py for each folder if you wish to run the files.
 
## WeatherPy
  
612 random unique cities have been selected by randomly generating GPS coordinates and finding the nearest city using the citipy library.
For each city, API calls have been made to openweathermap to collect the weather information below:

- Temperature (F)
- Humidity (%)
- Cloudiness (%)
- Wind Speed (mph)

Linear regression analysis was then conducted for the relationship between the Latitudes of the cities and their weather conditions to uncover any trends, found in the WeatherPy.ipynn file.

Some **observable trends** were:
1. There was a concave down shape in the City Latitude vs. Max Temperature (09/18/2021) scatter plot suggesting that maximum temperature drops when deviating away from the equator.
	Upon further investigation in the regression analysis for northern and southern hemispheres, there was strong negative of -0.82 and strong positive of 0.78 respectively.
	This correlations support the suggested statement: Maximum Temperature drops when deviating away from the Equator.
2. When obsevering the other regression analysis, there was almost no correlation between city latitude and other variables such as humidity, cloudiness and wind speed.
3. When observing the City Latitude vs. Humidity (09/18/2021) scatter plot, there were many cities with humidites above 60% humidity on this day.
4. Cloudiness was spread out when plotted against cloudiness, however there seem to be many cities with extreme levels of cloudiness.
	That is, many cities with maximum or close to maximum cloudiness (100%) and many cities with minimum cloudiness (0%).
5. When observing the City Latitude vs. Wind Speed (09/18/2021) scatter plot, most city windspeeds were below 20mph.

## VacationPy

A heatmap has been generated using the jupyter extension gmap for each of the selected cities and their humidity. A filter is then applied to spot the best weather conditions, that is:

- A max temperature lower than 80 degrees but higher than 70.
- Wind speed less than 10 mph.
- Zero cloudiness.

Using Google Places, API calls are then made to find the first hotel within 5km of each city. The details such as Hotel Name, City and Country can be found on the pin in the map.

![hotel_map](https://user-images.githubusercontent.com/85002751/213845917-ccac12c3-affb-4660-954d-1e7f9828ff23.png)
