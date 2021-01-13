# PDCurses

This is a Visual Studio 2019 project version of PDCurses ([website](https://pdcurses.org/)/[GitHub repo](https://github.com/wmcbrine/PDCurses)). 
I created it from the original PDCurses sources as retrieved from the PDCurses HitHub repo, to be able to properly debug an issue I ran into when trying to use PDCurses to marginally 
improve the college-time hobby project that is [R136](https://github.com/rbergen/R136). As it yielded a working version of PDCurses in the Visual Studio 2019 context that's familiar 
to many, I decided to create a repo for it, as well.

## Version

This incarnation of PDCurses is based on [PDCurses release 3.9](https://github.com/wmcbrine/PDCurses/releases/tag/3.9).

## Changes applied

To make PDCurses build in this form, the following changes were made to the original sources:
* All the source files built by \<pdcurses\>/wincon/Makefile.vc were put at the root of the VS 2019 project (original source files locations being \<pdcurses\>/, \<pdcurses\>/wincon, \<pdcurses\>/pdcurses and \<pdcurses\>/common)
* All global `#include`s of PDCurses headers were converted to local `#include`s
* The `is_nt` variable is fixed to `TRUE` in pdcscrn.c; Visual Studio has long stopped building for non NT-based versions of Windows anyway
* A `#pragma warning` was used to disable warning C28159 concerning the use of `GetTickCount()` in pdcscrn.c

Furthermore, changes were made to the VS 2019 project property defaults to make the project build.

## Credits

All credits go to the original PDCurses authors/maintainers.
