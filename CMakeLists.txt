#EIGEN3

add_library(eigen3 INTERFACE)

target_include_directories(eigen3 INTERFACE .)

target_link_libraries(eigen3 INTERFACE mkl thirdparty)

if(WIN32)
    target_compile_definitions(eigen3 INTERFACE
        EIGEN_USE_MKL_ALL
    )
endif()
