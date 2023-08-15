cmake_minimum_required(VERSION 3.24)

project(qsqlmysql)

add_definitions(-DQT_PLUGIN)

find_package(Qt5 COMPONENTS Core Sql REQUIRED) #Set Qt5_DIR CMake
find_package(unofficial-libmariadb CONFIG REQUIRED) #From vcpkg

add_library(qsqlmysql SHARED qsql_mysql.cpp main.cpp)

target_link_libraries(qsqlmysql PRIVATE Qt5::Core Qt5::Sql Qt5::SqlPrivate) 
target_link_libraries(qsqlmysql PRIVATE unofficial::libmariadb)
