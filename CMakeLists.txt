cmake_minimum_required(VERSION 3.25)
project(hello_world_app CXX)

# Set C++26 standard
set(CMAKE_CXX_STANDARD 26)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# Find Boost 1.90
# Use CONFIG mode to work with modern Boost installations
find_package(Boost 1.90 REQUIRED CONFIG)

# Find OpenSSL
find_package(OpenSSL REQUIRED)

# Add executable
add_executable(hello_world_app
    src/main.cpp
)

# Include directories
target_include_directories(hello_world_app PRIVATE
    ${Boost_INCLUDE_DIRS}
)

# Link libraries
# Boost.Asio is header-only, but we need to link against system libraries
target_link_libraries(hello_world_app PRIVATE
    Boost::headers
    OpenSSL::SSL
    OpenSSL::Crypto
    pthread
)

# Compiler flags
target_compile_options(hello_world_app PRIVATE
    -Wall
    -Wextra
    -pedantic
)
