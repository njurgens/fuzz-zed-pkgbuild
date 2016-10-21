# fuzz-zed-pkgbuild
This is a PKGBUILD for the fuzz type-checker for Z.

## Instruction

Clone this repository and run `makepkg` to build the package according to the `PKGBUILD` script.

    git clone https://github.com/njurgens/fuzz-zed-pkgbuild.git
    cd fuzz-zed-pkgbuild
    makepkg

Install the package with pacman.

    pacman -U fuzz-zed-3.4.1-1-x86_64.pkg.tar.gz


## About fuzz

The fuzz type-checker is a project by Mike Spivey. See his website for more details http://spivey.oriel.ox.ac.uk/mike/fuzz/.
