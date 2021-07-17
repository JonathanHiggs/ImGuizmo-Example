# ImGuizmo Example

Example app using [ImGui][ImGui] and [ImGuizmo][ImGuizmo] with [cmake][cmake] build system and the
[vcpkg][vcpkg] package manager

This takes the ImGuizmo example from their [repo][ImGuizmo]

## Setup

Assuming cmake and vcpkg are installed, first download ImGui and ImGuizmo packages from vcpkg

```
$ vcpkg install imgui:x64-windows imguizmo:x64-windows
```

Note: other triplets (x64-windows) are available. See the vcpkg [documentation][vcpkg-docs] for a
more complete explaination of installation and usage

Then to configure, cmake must be made aware of where the packages were installed to. Vcpkg supplies
a `CMAKE_TOOLCHAIL_FILE` which can be added to the cmake command line call (eg. from the git repo
root)

```
$ mkdir build
$ cd build
$ cmake .. -DCMAKE_TOOLCHAIL_FILE=C:\\path\\to\\vcpkg\\scripts\\buildsystems\\vcpkg.cmake
```

Another option is to use the cmake tools vscode extension (ms-vscode.cmake-tools). In
`.vscode/settings.json` add the toolchain path to the configure arguments

```json
{
    "cmake.configureArgs": [
        "-DCMAKE_TOOLCHAIN_FILE=C:\\path\\to\\vcpkg\\scripts\\buildsystems\\vcpkg.cmake"
    ]
}
```

This repo has vscode build and launch tasks added, so F5 run will run the cmake configure and build

Other IDEs that integrate with cmake will have an opportunity to specify the toolchain file


[Imgui]: https://github.com/ocornut/imgui
[ImGuizmo]: https://github.com/CedricGuillemet/ImGuizmo
[cmake]: https://cmake.org/
[vcpkg]: https://github.com/microsoft/vcpkg
[vcpkg-docs]: https://vcpkg.readthedocs.io/en/latest/README/