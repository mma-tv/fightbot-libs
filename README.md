# FIGHT BOT SETUP

## LIBRESSL 3.2.0
```
cd libressl*/
./configure --prefix="$HOME/.local"
make
make install
```

## TCL 8.6.10
```
patch -u tcl8*/generic/tcl.h -i tcl-emoji.patch
cd tcl8*/unix
./configure --prefix="$HOME/.local"
make
make install
```

## TCLLIB 1.20
```
cd tcllib*/
./configure --prefix="$HOME/.local"
make
make install
```

## TCLTLS 1.7.21
```
cd tcltls*/
./configure --prefix="$HOME/.local" --with-tcl="$HOME/.local/lib" --with-ssl=libressl --with-openssl-dir="$HOME/.local/lib"
make
make install
```

## TDOM 0.9.1
```
cd tdom*/
./configure --prefix="$HOME/.local" --with-tcl="$HOME/.local/lib" --with-tclinclude="$HOME/.local/include"
make
make install
```

## EGGDROP 1.8.4
```
patch -u eggdrop-*/src/tcl.c -i egg-utf-by-default.patch
cd eggdrop*/
export LD_RUN_PATH="$HOME/.local/lib"
./configure --prefix="$HOME/egg" --with-tcl="$HOME/.local/lib" --with-tcllib="$HOME/.local/lib/libtcl8.6.so" --with-tclinc="$HOME/.local/include/tcl.h" --with-tcl="$HOME/.local/lib" --with-sslinc="$HOME/.local/include" --with-ssllib="$HOME/.local/lib"
make config
make
make install
```
