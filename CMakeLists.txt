# Tutorial project: scripting basics in CMake

cmake_minimum_required(VERSION 3.12)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

project(Scripting VERSION 1.0.0)

# output a message using a variable declaration:
set(MY_VARIABLE "good.")
message(STATUS "The variable MY_VARIABLE in project ${PROJECT_NAME} is ${MY_VARIABLE}")

# conditional output
set(MY_VARIABLE2 "bad.")
if(MY_VARIABLE STREQUAL MY_VARIABLE2)
	message(STATUS "The two variables are the same.")
else()
	message(STATUS "The two variables are not the same.")
endif()

# while loop
set(num 4)
while(num LESS 11)
	message(STATUS "Value of num is ${num}.")
	math(EXPR num "${num} + 1")
endwhile()

# foreach loop
foreach(item IN ITEMS abc bcd cde def efg)
	message(STATUS "Item is: ${item}")
endforeach()

foreach(idx RANGE 0 15 3)
	message(STATUS "Index is: ${idx}")
endforeach()

add_executable(${PROJECT_NAME} src/main.cpp)
