cmake_minimum_required(VERSION 3.0)

project (CppCon2017liveNetworking)

#set environemt variable to location of netorking-ts include
include_directories ($ENV{NETWORKING_TS}/include)

remove_definitions(-std=c++14)
add_definitions(-std=c++1z -fcoroutines-ts -O2 -ferror-limit=1)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

set(Bin 01_simpleTimer)
set(Source ${Bin}.cpp)
add_executable (${Bin} ${Source})

set(Bin first)
set(Source ${Bin}.cpp)
add_executable (${Bin} ${Source})

set(Bin myclient)
set(Source ${Bin}.cpp)
add_executable (${Bin} ${Source})
target_link_libraries(${Bin} c++)

set(Bin easy)
set(Source ${Bin}.cpp)
add_executable (${Bin} ${Source})
target_link_libraries(${Bin} boost_system boost_thread)

set(Bin hard1)
set(Source ${Bin}.cpp)
add_executable (${Bin} ${Source})
target_link_libraries(${Bin} boost_system boost_thread)

set(Bin hard2)
set(Source ${Bin}.cpp)
add_executable (${Bin} ${Source})
target_link_libraries(${Bin} c++)

set(Bin stop1)
set(Source ${Bin}.cpp)
add_executable (${Bin} ${Source})
target_link_libraries(${Bin} boost_system boost_thread)

set(Bin over1)
set(Source ${Bin}.cpp)
add_executable (${Bin} ${Source})
target_link_libraries(${Bin} boost_system boost_thread)

set(Bin over2)
set(Source ${Bin}.cpp)
add_executable (${Bin} ${Source})
target_link_libraries(${Bin} boost_system boost_thread)
