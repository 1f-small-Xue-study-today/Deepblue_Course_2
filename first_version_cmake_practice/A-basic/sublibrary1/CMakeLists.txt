# Set the project name
project (sublibrary1)
set(LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/result)
add_library(hello.cpp SHARED ${LIBRARY_SRC})
# Add a library with the above sources
add_library(${PROJECT_NAME} src/hello.cpp)
add_library(sub::lib1 ALIAS ${PROJECT_NAME})

target_include_directories( ${PROJECT_NAME}
    PUBLIC ${PROJECT_SOURCE_DIR}/include
)
