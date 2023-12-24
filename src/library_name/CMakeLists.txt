add_library(library_name library.cc)

target_include_directories(library_name PUBLIC ${CMAKE_SOURCE_DIR}/include)
