# Modern C++ Starter

- [vcpkg](https://github.com/Microsoft/vcpkg), for package management, using classic mode. I don't like manifest mode, cause it introduces another two files: vcpkg.json and vcpkg-configuration.json.
- [cmake-presets](https://cmake.org/cmake/help/latest/manual/cmake-presets.7.html), for configuration sharing.

Principle: If a library can be downloaded by vcpkg, use `find_package` to include it. Or if a library can be added using CMake, use `add_subdirectory` to include it. Or you should build yourself then using `target_include_directories` and `target_link_libraries` to include it.

```txt
.
├── CMakeLists.txt            -- Top level of CMake configuration file
├── CMakePresets.json         -- For configuration sharing
├── configure                 -- vcpkg configure script, you should run this first
├── docs                      -- For docs
│   └── docs.md
├── include                   -- Include dir
├── src                       -- Source dir
├── tests                     -- Test dir
├── vcpkg-configuration.json  -- vcpkg registry configuration
├── vcpkg.json                -- vcpkg packages configuration
└── vendor                    -- Third-party vendor
    ├── CMakeLists.txt
    └── vcpkg                 -- Project's vcpkg
```

## Feature

1. Self-contained, you don't need to build and install dependencies yourself.
2. Modern package manager, vcpkg.
3. Easy-share cmake configuration using presets.
