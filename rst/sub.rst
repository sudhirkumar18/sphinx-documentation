Get WOEID
=========   
.. code-block:: python
   :emphasize-lines: 3,5

   def get_woeid(city_name):
      r = requests.get('https://www.metaweather.com/api/location/search/?query='+ str(city_name))
      woeid = r.json()[0]['woeid']
   return(get_weather_stats(woeid))


