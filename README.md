# Atom-tools

These are a set of scripts that ease the use of Atom.
Put all scripts in your PATH, and run them from your project's build directory.

## atom-autocomplete-clang

Generates a .clang_autocomplete configuration file for the provided component.
If a ".clang_complete.addon" file is present in the component root directory,
then this file is appended to the generated file. This allows to add other
compiler options.

## atom-buid-gen

Generates an atom-build configuration file so that the component can be build
within atom. The following targets are generated:

- all
- clean
- check

## atom-rtags-gen

Generates a "compile_commands.json" for the component if it does not exist, and
adds it to the rtags rdm indexer daemon. Using the "last-cursor-position"
package in combination with rtags allows to go back to previous code locations.

This script requires bear to be installed on the system :

    https://github.com/rizsotto/Bear/tree/master/libear

On 64bit systems, bear must be compiled and installed for both 32 and 64 bit
architectures. Select the architecture when runing cmake. For 32 bit systems:

    CFLAGS=-m32 CXXFLAGS=-m32 cmake -DCMAKE_INSTALL_PREFIX=/home/xx/local

and for 64bit systems:

    CFLAGS=-m64 CXXFLAGS=-m64 cmake -DCMAKE_INSTALL_PREFIX=/home/xx/local
