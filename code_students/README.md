## Code

The code is written in C++ and requires C++17 and `cmake` to build.
Additionally, we require hdf5 used for writing data to disk.
The project is a simple finite-volume hydrodynamics code with second-order spatial reconstruction and second-order time-integration.
It uses a semi-discrete version of the finite-volume scheme with an HLL Riemann solver.

### Prerequesites

The code requires hdf5, which should be available via your software environment.
Additionally, it uses Googletests.
This can be cloned from `git@github.com:google/googletest.git`.
Copy this into a directory of your choice, then go to the main directory, created a directory `build` and in this directory execute

    cmake .. -DBUILD_GMOCK=OFF -DCMAKE_INSTALL_PREFIX=/your/install/path

where you need to specify the install path.
Finally, build the code via `make install`

### Directory structure.

The project uses `cmake` to build.
You can find the file `CMakeLists.txt` in the code's main directory.
Header files can be found in `include` and its subdirectories.
Similarly, `src` and it's sub directories hold the source files.
Additionally, `apps` contains all source files holding `main` functions, thus allowing different setups of the code.
That also means, you can create a new setup, by copying one of the source files in `apps` and extending the `CMakeLists.txt` in the same directory correspondingly.

### Building the code

You can build the code by creating a build-directory, e.g., via `mkdir build`.
Next, change into that directory, execute `cmake ..` and `make install`.
This will install the executables in the directory `bin` in the main code directory.
