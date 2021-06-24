# cmake-project-template-cpp
A sample CMake project, using C++ sources.

## Building

Run the included `makebuilds` script to have `cmake`<br>
create Unix-Makefile builds in the following modes:
- `Debug`
- `Release`
- `MinSizeRel`
- `RelWithDebInfo`

```
% ./makebuilds
```

A `build/make` subdirectory will be created with subdirectories<br>
of the modes described above. 

If we want to create a `Debug` build of the program in the `demo` directory<br>
(which will also build the sources in the `src` directory):

```
make -C ./build/make/Debug/demo
```

Generally, you would invoke `make` as follows:
```
make -C ./build/make/[build-mode]/[target-name]
```

After running `make`, you can run the `demo` executable:
```
./build/make/Debug/demo/demo
```

Generally:
```
./build/make/[build-mode]/[target-name]/[executable-name]
```

### Alternate build systems

If you want to use an alternative build system, i.e. Xcode or Visual Studio<br>
(see the list of supported generators on your system using `cmake -help`), invoke the following:
```
% cmake -S ./ -B ./build/[generator-name] -G "[generator-name]"
```

For example, for Xcode:
```
% cmake -S ./ -B ./build/xcode -G "Xcode"
```
