set(LIBNAME "tinyxml")

# Sources
include_directories("${CMAKE_CURRENT_SOURCE_DIR}")
file(GLOB SOURCE_FILES *.cpp)

add_definitions("-DORK_API=__declspec(dllexport)" "-DTIXML_USE_STL")

# Create a static library
add_library(${LIBNAME} STATIC ${SOURCE_FILES})

link_directories(${CMAKE_CURRENT_BINARY_DIR})

# Install library
INSTALL(TARGETS ${LIBNAME} LIBRARY DESTINATION ${LIB_INSTALL_DIR} ARCHIVE       DESTINATION  ${LIB_INSTALL_DIR})

