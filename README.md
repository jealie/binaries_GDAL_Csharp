# Binaries of the GDAL libraries for C\#
GDAL compiled with C#/Mono bindings, for linux (64 and 32 bits).

GDAL ships with [C# bindings](https://trac.osgeo.org/gdal/wiki/GdalOgrInCsharp) - however their compilation is not straightforward for linux. This repository aims to fill this gap by providing reasonably up-to-date, pre-compiled GDAL bindings for C#. The current bindings are for GDAL 2.1.1.

The binaries are provided in this repository to enable automatic installation of LANDIS-II in linux. Step-by-step compilation instructions are also available [here](https://github.com/jealie/binaries_GDAL_Csharp/blob/master/compilationNotes.txt) in case you want to build the bindings yourself.

## Using these libraries in your C# projects

To deploy your mono projects using GDAL on linux, you will need to ship the following files with it: `libgdal.so.20`, `libgdal_wrap.so` and `gdal_csharp.dll` from the right directory (`linux32` or `linux64`). The `gdal.tar.gz` compressed archives contain these three files.

Make sure that mono can find the libraries at runtime, by invoking for example `LD_PRELOAD`:
```shell
LD_PRELOAD="/path/to/libgdal.so /path/to/libgdal_wrap.so" mono your_program.exe
```
Make also sure that mono can find the gdal\_sharp.dll file: this can be done easily by copying/linking it in the same directory as your\_program.exe
