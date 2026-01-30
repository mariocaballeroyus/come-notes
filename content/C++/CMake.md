[[C++]]
## Basic Configuration

```CMake
cmake_minimum_required(VERSION 3.10)

project(VectorComputation VERSION 1.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
```

## Libraries
```CMake
add_library(mylibrary
	src/somefile.cpp
	// all source files (gather recursively if needed)
)
target_include_directories(mylibrary
	${CMAKE_CURRENT_SOURCE_DIR}/inc
)
```
## Subdirectories

In CMake, a “subdirectory” simply refers to a **subfolder in your project** that has its **own `CMakeLists.txt`** file.

```CMake
add_subdirectory(mylibrary)
```

## Executables

```Cmake
add_executable(myexecutable 
	main.cpp
	// add other source files for linking
)
```

### Linking Libraries

```CMake
target_link_libraries(myexecutable PRIVATE
	mylibrary
	// as many libraries as needed
)
```