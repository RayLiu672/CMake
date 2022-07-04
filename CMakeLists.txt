cmake_minimum_required(VERSION 3.16.3)

project(TestCode) 
# reference TestCode as Project_Name # source: main.cpp
# adder.cpp does not need to be added into object (Top level)
# builds our main
add_executable(${PROJECT_NAME} main.cpp)

# builds library(LOW LEVEl)
add_subdirectory(Adder)

# Tell them where includes are so we can put #include adder.h instead of #include Adder/adder.h
target_include_directories(${PROJECT_NAME} PUBLIC Adder)

target_link_directories(${PROJECT_NAME} PRIVATE Adder)

# links the library to executiable can add more by spacing adder adder1 adder2 etc
target_link_libraries(${PROJECT_NAME} adder)



# To run in cmd: ./TestCode

# Source is folder containing everything (TestCode)
# Build generally called build folder 

# --------------------------------------------------------------------------------To compile ----------------------------------------------------------
# -S . current folder(TestCode) -B out/build or whatever path from source folder to build 
#cmake -S . -B out/build/

# -C is cd equivalent
# make -C out/build/ 

# Gives results
# .out/build/TestCode 
