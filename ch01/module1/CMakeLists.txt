#run "cmake -S ."

cmake_minimum_required(VERSION 3.26.0)

project(ModuleExample)

include (TestBigEndian)

test_big_endian(IS_BIG_ENDIAN)

if(IS_BIG_ENDIAN)

message("BIG_ENDIAN")

else()

message("LITTLE_ENDIAN")

endif()