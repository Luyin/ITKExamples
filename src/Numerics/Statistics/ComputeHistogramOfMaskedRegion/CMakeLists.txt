cmake_minimum_required(VERSION 3.10.2)

project(ComputeHistogramOfMaskedRegion)

find_package(ITK REQUIRED)
include(${ITK_USE_FILE})


add_executable(ComputeHistogramOfMaskedRegion Code.cxx)
target_link_libraries(ComputeHistogramOfMaskedRegion ${ITK_LIBRARIES})

install(TARGETS ComputeHistogramOfMaskedRegion
  DESTINATION bin/ITKExamples/Numerics/Statistics
  COMPONENT Runtime
  )

install(FILES Code.cxx CMakeLists.txt
  DESTINATION share/ITKExamples/Code/Numerics/Statistics/ComputeHistogramOfMaskedRegion/
  COMPONENT Code
  )


enable_testing()
add_test(NAME ComputeHistogramOfMaskedRegionTest
  COMMAND ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/ComputeHistogramOfMaskedRegion)

