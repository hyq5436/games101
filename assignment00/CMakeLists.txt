# target
set(TARGET_NAME Transformation)

find_package(Eigen3 REQUIRED)

# add the executable
add_executable(${TARGET_NAME} main.cpp)

# include directories
target_include_directories(${TARGET_NAME}
    PUBLIC
        ${GTEST_INCLUDE_DIRS}
        ${EIGEN3_INCLUDE_DIRS})

# preprocessor
# target_compile_definitions(${TARGET_NAME} PUBLIC ASIO_STANDALONE)

# gcc feature
set(GCC_UNDEFINED_FLAG "-fsanitize=undefined")

# compile options
# target_compile_options(${TARGET_NAME} PUBLIC ${GCC_UNDEFINED_FLAG})

# link options
#target_link_options(${TARGET_NAME} PUBLIC ${GCC_UNDEFINED_FLAG})

# link dependency
target_link_libraries(${TARGET_NAME} PUBLIC ${CMAKE_THREAD_LIBS_INIT})
