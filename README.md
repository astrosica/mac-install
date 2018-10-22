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


## Karma
For more information, visit:

* http://www.atnf.csiro.au/computing/software/karma/
* ftp://ftp.atnf.csiro.au/pub/software/karma/README
* ftp://ftp.atnf.csiro.au/pub/software/karma/

Make sure to download both the appropriate distribution tarbell and the relevant common.tar. For MacOSX running Sierra this was karma-1.7.20-x86_64_Darwin-15.5.tgz andkarma-1.7.20-common.tgz.

### Directions for installation:

Move over to /usr/local directory and copy distributions over.
```
cd /usr/local
sudo cp ~/Downloads/karma-1.7.20-* .
```

Unpack tar files.
```
sudo gunzip karma-1.7.20-x86_64_Darwin-15.5.tgz
sudo gunzip karma-1.7.20-common.tgz
sudo tar -xzvf karma-1.7.20-x86_64_Darwin-15.5.tar
sudo tar -xzvf karma-1.7.20-common.tar
```
Create a symbolic link that points to your karma distribution
```
sudo ln -s /usr/local/karma-1.7.20/x86_64_Darwin-15.5/ /usr/local/karma/
```

Add the distribution directory and KARMABASE variable to bash profile.
```
export PATH="/usr/local/karma/bin:$PATH"
export KARMABASE="/usr/local/karma"
```

## Glueviz
For more information, visit:

* http://docs.glueviz.org/en/stable/index.html

### Directions for installation:

Install via Anaconda.
```
conda install glueviz
```

Note that `Glueviz` also requires `Pandas`, `PyQt5`, `Qt Console`, `ipykernel`, `h5py`, `xlrd`, and `astrodendro` (see below).

## Pandas
For more information, visit:

* http://pandas.pydata.org/

### Directions for installation:

Install via Anaconda.
```
conda install pandas
```

## PyQt5
For more information, visit:

* https://www.riverbankcomputing.com/software/pyqt/intro

### Directions for installation:

Install via Homebrew.
```
brew install pyqt5
```

## Qt Console
For more information, visit:

* https://qtconsole.readthedocs.io/en/stable/

### Directions for installation:

Install via Anaconda.
```
conda install qtconsole
```

## iPykernel
For more information, visit:

* https://pypi.org/project/ipykernel/

### Directions for installation:

Install via Anaconda.
```
conda install ipykernel
```

## h5py
For more information, visit:

* http://www.h5py.org/

### Directions for installation:

Install via Anaconda.
```
conda install h5py
```

## xlrd
For more information, visit:

* https://xlrd.readthedocs.io/en/latest/

### Directions for installation:

Install via Anaconda.
```
conda install xlrd
```

## astrodendro
For more information, visit:

* https://dendrograms.readthedocs.io/en/stable/
* https://pypi.org/project/astrodendro/

### Directions for installation:

Download tar file from PyPI.

Move over to /usr/local directory and copy tar file over.
```
cd /usr/local
sudo cp ~/Downloads/astrodendro-* .
```

Unpack tar files.
```
sudo gunzip astrodendro-0.2.0.tar.gz
sudo tar -xzvf astrodendro-0.2.0.tar
```

Move into astrodendro directory and install via setup.py.
```
cd ./astrodendro-0.2.0
sudo python setup.py install
```
