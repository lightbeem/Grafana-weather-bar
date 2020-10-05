# Grafana-weather-bar

Create a clean and minimal weather stats bar in Grafana.

![screenshot](/Grafana_weather_bar_screenshot.png)

Warning: You are seeing a work in progress. I am not yet familiar with how to set up variables in Grafana, so there will be some manual changes you need to make to the JSON code to match what you have coming from InfluxDB. Below is a list of general steps I took to get this working. Your mileage may vary, but am happy for anyone to help make this a bit cleaner.

# AQI and Ozone data
Start with bastienwirtz's [aqi_watcher](https://github.com/bastienwirtz/aqi_watcher). It uses python to pull in data from a few api sources and then inserts into InfluxDB.


# Temp, Humidity, Visibility, Wind, Rain, etc
Note that combining current and forecast data may not be coming through the same API. I haven't spent the time to figure out why I don't have forecast data being capture.
1. Head to openweathermap.org for your API key.
2. Determine your city_id following [this write up](https://www.dmopress.com/openweathermap-howto/).
2. Add API key and city id to telegraf config. Restart telegraf.

# Grafana
Update CITYHERE and ZIPCODEHERE in dashboard.json and create new dashboard via Grafanas import function. This is where I'm the least clear about all the steps. If some tries this and runs into issues or knows what the proper way is to share this out, please open an Issue
