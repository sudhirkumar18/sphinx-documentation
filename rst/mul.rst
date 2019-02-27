Get Weather
=========== 
.. code-block:: python
   :emphasize-lines: 3,5

   def get_weather_stats(woeid):
      date = datetime.datetime.now().strftime("%Y/%m/%d")
      r = requests.get('https://www.metaweather.com/api/location/'+str(woeid)+"/"+date)
      weather_state = r.json()[0]['weather_state_name']
      temperature = r.json()[0]['the_temp']
   return(weather_state,temperature)

