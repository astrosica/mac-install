# Installation procedures for MacOS.

## Miriad
For more information, visit:

* http://www.atnf.csiro.au/computing/software/miriad/
* http://ftp.atnf.csiro.au/pub/software/miriad/

Make sure to download both the appropriate distribution tarbells. For MacOSX running Sierra this was miriad-darwin_x86_64.tar.bz2 and miriad-common.tar.bz2.

### Directions for installation:

Move over to /usr/local directory and copy distributions over.
```
cd /usr/local
sudo cp ~/Downloads/miriad-* .
```

Unpack tar files.
```
sudo bunzip2 miriad-darwin_x86_64.tar.bz2
sudo bunzip2 miriad-common.tar.bz2
sudo tar -xzvf miriad-darwin_x86_64.tar
sudo tar -xzvf miriad-common.tar
```

Add the distribution directory and MIR variable to bash profile.
```
export PATH="/usr/local/miriad/darwin_x86_64/bin:$PATH"
export MIR=”/usr/local/miriad”
```

Note that `Miriad` also requires `RPFITS` and `WCSLIB` (see below).


## RPFITS
For more information, visit:

* http://www.atnf.csiro.au/computing/software/rpfits.html

Make sure to download both the appropriate distribution tarbells. For MacOSX running Sierra this was rpfits-2.24_darwin.tar.gz and rpfits-2.24.tar.gz.

### Directions for installation:

Move over to /usr/local directory and copy distributions over.
```
cd /usr/local
sudo cp ~/Downloads/rpfits-* .
```

Unpack tar files.
```
sudo gunzip rpfits-2.24.tar.gz
sudo gunzip rpfits-2.24_darwin.tar.gz
sudo tar -xzvf rpfits-2.24.tar
sudo tar -xzvf rpfits-2.24_darwin.tar
```


## WCSLIB
For more information, visit:

* http://www.atnf.csiro.au/people/Mark.Calabretta/WCS/
* http://www.atnf.csiro.au/people/mcalabre/WCS/wcslib/

The `WCSLIB` package first needs `CFITSIO` to be installed (see below).

Make sure to download the wcslib.tar.bz2 distribution.

### Directions for installation:

Move over to /usr/local directory and copy distributions over.
```
cd /usr/local
sudo cp ~/Downloads/wcslib.tar.bz2 .
```

Unpack tar files.
```
sudo bunzip2 wcslib.tar.bz2
sudo tar -xzvf wcslib.tar
```

Move into new wcslib directory and configure.
```
cd ./wcslib-5.19.1/
sudo ./configure --without-pgplot LIBS="-pthread -lm"
```

Replace 8 with no. CPU threads.
```
sudo make -j8
sudo make check
```

Complete installation.
```
sudo make install
```



## CFITSIO
For more information, visit:

* https://heasarc.gsfc.nasa.gov/fitsio/fitsio.html

Make sure to download both the latest cfitsio_latest.tar.gz distribution. This can always be accessed with the following link: http://heasarc.gsfc.nasa.gov/FTP/software/fitsio/c/cfitsio_latest.tar.gz

### Directions for installation:

Move over to /usr/local directory and copy distributions over.
```
cd /usr/local
sudo cp ~/Downloads/cfitsio_latest.tar.gz .
```

Unpack tar file.
```
sudo tar xzf cfitsio_latest.tar.gz
```

Add the distribution directory and MIR variable to bash profile.
```
export PATH="/usr/local/miriad/darwin_x86_64/bin:$PATH"
export MIR=”/usr/local/miriad”
```

Move into new cfitsio directory and configure.
```
cd ./cfitsio
sudo ./configure
```

Run make and complete installation.
```
sudo make
sudo make install
```

Add distribution directory to bash_profile.
```
export PATH=”/usr/local/cfitsio:$PATH”
```
