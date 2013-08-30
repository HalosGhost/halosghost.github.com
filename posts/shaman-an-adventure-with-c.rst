.. title: Shaman, an adventure with C
.. slug: shaman-an-adventure-with-c
.. tags: 
.. description: 
.. date: 2013/08/29 19:30:44
.. link: 
.. nocomments: True

I have been proficient with scripting languages for a long while now, and once upon a time I knew something about Python (but that has long since been forgotten). Having switched to a very minimalist desktop environment (the whole thing with all my customizations is ~1500 sloc of C), and dealing with several C programs (along with having been made an `official contributor <https://github.com/TrilbyWhite/alopex.git>`_ to one of the projects written entirely in C), I felt it necessary for me to pick up one of the more universal languages and C seemed the obvious choice. I've messed around with a few small C programs as ways of getting my feet wet (i.e., `vulpes <https://github.com/HalosGhost/vulpes.git>`_, `immio <https://github.com/HalosGhost/immio.git>`_). However, a short while ago, I stumbled upon an awesome tool called `weatherman <http://darkhorse.nu/weatherman/>`_, and it inspired me to begin working on an alternative written in C using the `NOAA <http://forecast.weather.gov>`_ as a backend rather than weatherbug. 

Thus was born, `shaman <https://github.com/HalosGhost/shaman.git>`_. Originally, I really only wanted it to be able to fetch only the current conditions of a given location so that I could use it to display a relevant weather icon on my statusbar (using vulpes). But, as is the way with these projects, it evolved to also fetch temperature, and now, at the time of writing this post, ``shaman`` is capable of fetching the following:

#. Reporter name, location and coordinates
#. Rudimentary hazardous/severe weather warnings
#. Current weather conditions
#. Temperature
#. Heat Index
#. Wind reports
#. Humidity
#. Dew Point
#. Visibility
#. Pressure

It is also capable of printing mesurements in Imperial and Metric units. I am also working on implementing 7-day forecasts.

Currently, there are a couple of C conventions that ``shaman`` does not adhere to (these are planned enhancements that I just need to learn before I can implement). These include native use of ``libcurl`` rather than calling a shell and executing ``curl`` itself, and using offsets in loops rather than using pointer arithmatic. I do, however, want to finish implementing my planned 7-day forecast feature so ``shaman`` can be functionally complete for its first version before I go and start messing around with the backends that I don't fully understand.

There is also one other possible feature that I am considering but I do not know if I will ever implement. If you have ever used the ``date`` command or the backend which it utilizes called ``strftime``, then you are likely familiar with their format-code printing system. That is, you pass a string to ``date`` which tells it what you want to see and how they should be printed and ``date`` complies. Currently, ``shaman`` prints information in a pre-formatted style that cannot be edited without editing source. After having released my code on github and publishing an announcement for the project on the `Archlinux BBS <https://bbs.archlinux.org/viewtopic.php?id=168620>`_, it has been requested that I add a similar feature (this is something that ``weatherman`` actually does too) so that a user may determine the exact output and format of the data which ``shaman`` fetches. This would require a great increase of code but would make its use extremely versatile.

Should 7-day forecasts go well, and the migration to ``libcurl`` and pointer arithmatic go well, then this may very well become the last thing to implement before considering ``shaman`` to be essentially feature-complete. In the meantime, I have plenty to keep me busy on this project.
