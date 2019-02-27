

.. mytestcase documentation master file, created by
   sphinx-quickstart on Mon Feb 25 12:35:06 2019.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

**Welcome TO Weatherbot Documentation!**
======================================
.. image:: /image/download.jpeg
Audio_to_text function
======================   
.. code-block:: python
   :emphasize-lines: 3,5
   
   def Audio_to_text(audio):
      try:
          print("You said " + r.recognize_google(audio))
      except sr.UnknownValueError:
          print("Could not understand audio")
      except sr.RequestError as e:
          print("Could not request results; {0}".format(e))

	city_name = str(r.recognize_google(audio).split(' ')[-1])
    return(city_name)

Get_Woeid function
==================   
.. code-block:: python
   :emphasize-lines: 3,5

   def get_woeid(city_name):
      r = requests.get('https://www.metaweather.com/api/location/search/?query='+ str(city_name))
      woeid = r.json()[0]['woeid']
   return(get_weather_stats(woeid))

Get_weather_stats function
========================== 
.. code-block:: python
   :emphasize-lines: 3,5
   
   def get_weather_stats(woeid):
      date = datetime.datetime.now().strftime("%Y/%m/%d")
      r = requests.get('https://www.metaweather.com/api/location/'+str(woeid)+"/"+date)
      weather_state = r.json()[0]['weather_state_name']
      temperature = r.json()[0]['the_temp']
   return(weather_state,temperature)
.. toctree::
   :maxdepth: 3
   :caption: Contents:
   
   /rst/add
   /rst/sub
   /rst/mul

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
