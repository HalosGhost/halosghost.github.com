.. link: 
.. description: 
.. title: Shaman, revamped!
.. slug: shaman-revamped
.. tags: 
.. date: 2013/12/10 22:08:28
.. nocomments: True

Upon looking back at my code of Shaman 1.x, I discovered that it was really quite disgusting. It was dense, difficult to read and poorly implemented. Furthermore, many of the conventions I used in the first version were entirely not portable and incredibly inefficient. So, I resolved, a couple of weeks ago, to begin work on the second major release which would fix essentially all of the problems 1.x experienced.

First, and foremost, this means that the non-native C functions I used (namely curl and grep) had to be replaced by their native C counterparts. As a result, the work underway for `Shaman 2.x <https://github.com/HalosGhost/shaman>`_ will use a variety of libraries that the 1.x branch did not. Most obviously, this means it will link to libcurl rather than call curl inside a shell. Beyond the native implementations, the 2.x branch will be using much cleaner code conventions to complete the task delegated to it. The improvments in this area are clear everywhere. The following is a short list of all the improvments that users can expect:

* `libcurl <http://curl.haxx.se/libcurl/>`_ for native data fetching
* C's `getopt <https://www.gnu.org/software/libc/manual/html_node/Getopt.html>`_ for more sensible parsing of command-line arguments
* `libxml2 <http://www.xmlsoft.org/downloads.html>`_ instead of giant, disgusting and essentially obfuscated fscanfs for parsing the fetched data
* `libconfig <http://www.hyperrealm.com/libconfig/>`_ for sensible configuration parsing
* General code cleanliness and conventions (like prototypes and declaring variables where needed; not all on the stack)
* strftime-like format string for simpler and more configurable output according to user-needs

The end-result of this update will mean a few things. First of all, the final binary will certainly be a bit larger than 1.x. Having said that, it will run more efficiently, much faster and the weather data will be formatted exactly how users wish it to be which should mean easier parsing and more flexibility for a greater number of use-cases.

Though the work on updating Shaman has really just begun, a great deal of it has been completed. Because I have never worked with any of the libraries mentioned above before, I suspect that the final project is still a way off. Still, development is active and you can follow my progress on my `GitHub <https://github.com/HalosGhost/>`_. As always, pull requests, suggestions and feature requests will always be appreciated—though I would ask that everyone hold off on bug reports until the testing stage is reached.
