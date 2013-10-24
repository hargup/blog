Make your Laptop blink
======================

My year was searching for ways to change the brigtness of my laptop using cli.
And I found out that file `/sys/class/backlight/intel_backlight/brightness` on
system controls the brightness, so you can either edit it manually or write
programs to control it in crazy ways. One can be to make you laptop blink. 

.. code-block:: python 

    import time
    max_brightness_file = open("/sys/class/backlight/intel_backlight/max_brightness","r")
    max_brightness = int(max_brightness_file.read())

    i = max_brightness 
    start_time = time.time()
    end_time = time.time()
    running_time = int(raw_input()) 

    while (end_time - start_time) < running_time:
        brightness_file = open("/sys/class/backlight/intel_backlight/brightness","w")
        i = int(i-1)%max_brightness 
        brightness_file.write(str(i))
        brightness_file.close()
        end_time = time.time()

    brightness_file = open("/sys/class/backlight/intel_backlight/brightness","w")
    brightness_file.write(str(max_brightness))

Run the program with root permision, with parameter as the blinking time.


.. author:: Harsh Gupta 
.. categories:: linux 
.. tags:: linux 
.. comments::
