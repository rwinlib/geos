GEOS 3.5.0. Compiled with:

	export CC="gcc -02"
	export CXX="g++ -02"
	../geos-3.5.0/configure --enable-static --enable-shared --disable-inline

We must disable inline, otherwise static linking does not work for C++!

Note that the geos autoconf script defaults to adding debug symbols with "-g". 
Therefore I manually removed them afterwards.
This reduces the size of each static library from 32MB to 4MB.


    strip -g *.a


This same library is also included with rwinlib/gdal2.

