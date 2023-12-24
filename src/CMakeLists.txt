add_executable(run run.cc)

find_package(fmt REQUIRED)

target_link_libraries(run library_name fmt::fmt)

add_subdirectory(library_name)
