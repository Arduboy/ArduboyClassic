Arduboy Classic Library
===============
This documentation provides provides instructions for installing and using the
Arduboy Classic library, which is compatible with the Arduino 1.0.x platform,
and is fully compatible with release 1.1 of the 
[Arduboy Library](https://github.com/Arduboy/Arduboy/releases/tag/v1.1).

## About the Library
The Arduboy Classic Library provides a programming interface for the creation
of games and applications that run on the Arduboy handheld device. The Arduboy
is supported by the Arduino platform and is powered by an Atmel ATmega32u4 MCU.

More information can be found at [https://arduboy.com](https://www.arduboy.com).

## Using the Library
To use the Arduboy library, it must be installed and then included in your
project.

#### Installing Arduboy Classic Library
There are several ways to install the Arduboy Classic Library for use in your
projects. The recommended method, and easiest to use when getting started, or
when making simple apps, is through the Arduino IDE.

##### Adruino IDE - *Recommended*
After installing the 
[Arduino Classic IDE](https://www.arduino.cc/en/Main/OldSoftwareReleases#1.0.x),
the Arduboy Classic Library can be added to the Arduino 1.0.x IDE through 
the main menu under `Sketch > Import Library > Add Library...`.

Select a local zip file of the Arduboy Classic library. Instructions for
downloading the Arduboy Classic archive can be found in the next section.


##### Download an Archive
Archived versions of the Arduboy Classic Library can be downloaded and
uncompressed to your local Arduino *libraries* folder. See the sub-section
*Where to Install*, found at the bottom of this section. 

> **Downloads**
> ([zip](https://github.com/Arduboy/ArduboyClassic/archive/1-1-stable.zip))

##### Use Source Management (Git)
Install the library by cloning its repository. This will put you on the `master`
branch, which is the newest version of the library.
~~~bash
git clone https://github.com/Arduboy/ArduboyClassic/tree/1-1-stable.git
~~~

#### Where to Install
The library should be installed into your user's home Arduino `libraries`
directory. Refer to the following list for the location of the Arduino
`libraries` folder.

##### Linux
~~~
/home/username/Documents/Arduino/libraries
~~~

##### Mac
~~~
/Users/username/Documents/Arduino/libraries
~~~

##### Windows
~~~
C:\Users\username\My Documents\Arduino\libraries
~~~

If you don't find the `libraries` folder in one of the above locations, you can
determine its location using the navigation menu `File > Preferences`. In the
`Settings` tab will be a `Sketchbook location:` field. The `libraries` folder
will be in the folder set in this field.

### Including the Arduboy Library
To use the Arduboy library in your own sketches, include the `Arduboy.h`
header file. To do so, add the following line to the top of your `.ino` file.

~~~C
#include <Arduboy.h>
~~~

You can have the Arduino IDE add `#include "Arduboy.h"` to your sketch
automatically by using the navigation menu `Sketch > Include Library > Arduboy`.

### Board Selection
Select the **Leonardo** board as the target platform.

### Examples
Example games and source can be found in the `examples` directory.

#### Playing Examples
Find and play an example by opening it through the Arduino IDE, compiling, and
uploading the example to the Arduboy.
Examples can be found in the Arduino IDE in the navigation menu under, 
`File > Examples > Arduboy > Example_Name`.

### Running on a Development Board
To run this library on a development Arduboy board, edit `core/core.h` so that
`#define AB_DEVKIT` is uncommented and `#define ARDUBOY_10` is commented out.

~~~cpp
//#define ARDUBOY_10   // compile for the production Arduboy v1.0
#define AB_DEVKIT      // compile for the official dev kit
~~~

### Sketches Already Including the Arduboy Library
Sketches that include copies of the Arduboy library may not compile if the
Arduboy library has been installed system wide. In these cases the Arduino
compiler will try and link the system Arduboy library source with the local
header file, which can cause compilation errors if the local library source
differs from the system's Arduboy source.

To compile sketches that have included copies of the Aruboy Library,

• Remove the local `Arduboy.cpp` and `Arduboy.h` files and try recompiling.
This will only work in some cases.

**OR**,

• Rename `Arduboy.h` to `CustomArduboy.h` (or a similar name) and add,
`#include "CustomArduboy.h"` to the sketch's `.ino` file. 
