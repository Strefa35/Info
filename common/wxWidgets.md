# wxWidgets

## Compiling and getting started

- <https://wiki.wxwidgets.org/Compiling_and_getting_started>
- [FindwxWidgets.cmake](https://gitlab.kitware.com/cmake/cmake/blob/master/Modules/FindwxWidgets.cmake#L38)

## Build wxWidgets

Reference: <https://www.binarytides.com/install-wxwidgets-ubuntu/>

```bash
mkdir gtk-build && cd gtk-build
../configure --disable-shared --enable-unicode
make
```

## Configure library

```bash
sudo apt-get remove --purge wxWidgets-3.0.2   # remove old version
cd wxWidgets-3.1/buildGTK
sudo make install
sudo ldconfig
```
