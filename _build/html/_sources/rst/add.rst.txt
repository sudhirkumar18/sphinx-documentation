Audio to text
=============   
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


