cmake_minimum_required(VERSION 3.10.2)

project(CreateListOfSamplesFromImageWithoutDuplication)

find_package(ITK REQUIRED)
include(${ITK_USE_FILE})


add_executable(CreateListOfSamplesFromImageWithoutDuplication Code.cxx)
target_link_libraries(CreateListOfSamplesFromImageWithoutDuplication ${ITK_LIBRARIES})

install(TARGETS CreateListOfSamplesFromImageWithoutDuplication
  DESTINATION bin/ITKExamples/Numerics/Statistics
  COMPONENT Runtime
  )

install(FILES Code.cxx CMakeLists.txt
  DESTINATION share/ITKExamples/Code/Numerics/Statistics/CreateListOfSamplesFromImageWithoutDuplication/
  COMPONENT Code
  )


enable_testing()
add_test(NAME CreateListOfSamplesFromImageWithoutDuplicationTest
  COMMAND ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/CreateListOfSamplesFromImageWithoutDuplication)
