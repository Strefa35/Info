
## Compiling and getting started
    https://wiki.wxwidgets.org/Compiling_and_getting_started
    https://gitlab.kitware.com/cmake/cmake/blob/master/Modules/FindwxWidgets.cmake#L38


## Build wxWidgets
    https://www.binarytides.com/install-wxwidgets-ubuntu/

    mkdir gtk-build
    cd gtk-build/
    ../configure --disable-shared --enable-unicode
    make

## Configure library
    1. sudo apt-get remove --purge wxWidgets-3.0.2
    2. cd wxWidgets-3.1/buildGTK
    3. sudo make install
    4. sudo ldconfig

