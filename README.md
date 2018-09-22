# Installation procedures for MacOS.

## Miriad
For more information, visit:

* http://www.atnf.csiro.au/computing/software/miriad/
* http://ftp.atnf.csiro.au/pub/software/miriad/

Make sure to download both the appropriate distribution tarbells. For MacOSX running Sierra this was miriad-darwin_x86_64.tar.bz2 and miriad-common.tar.bz2.

Directions for installation:

```
cd /usr/local
sudo cp ~/Downloads/miriad-* .
sudo bunzip2 miriad-darwin_x86_64.tar.bz2
sudo bunzip2 miriad-common.tar.bz2
sudo tar -xzvf miriad-darwin_x86_64.tar
sudo tar -xzvf miriad-common.tar
export PATH="/usr/local/miriad/darwin_x86_64/bin:$PATH"
export MIR=”/usr/local/miriad”
```
