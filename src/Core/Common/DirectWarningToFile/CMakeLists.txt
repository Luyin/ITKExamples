cmake_minimum_required(VERSION 3.10.2)

project(DirectWarningToFile)

find_package(ITK REQUIRED)
include(${ITK_USE_FILE})


add_executable(DirectWarningToFile Code.cxx)
target_link_libraries(DirectWarningToFile ${ITK_LIBRARIES})

install(TARGETS DirectWarningToFile
  DESTINATION bin/ITKExamples/Core/Common
  COMPONENT Runtime
  )

install(FILES Code.cxx CMakeLists.txt
  DESTINATION share/ITKExamples/Code/Core/Common/DirectWarningToFile/
  COMPONENT Code
  )


enable_testing()
add_test(NAME DirectWarningToFileTest
  COMMAND ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/DirectWarningToFile)

