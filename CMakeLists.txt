cmake_minimum_required(VERSION 3.14)
project(fuzzer VERSION 1.0 LANGUAGES CXX)

set(SRC_FILES
  FuzzerCrossOver.cpp
  FuzzerDataFlowTrace.cpp
  FuzzerDriver.cpp
  FuzzerExtFunctionsDlsym.cpp
  FuzzerExtFunctionsWeak.cpp
  FuzzerExtFunctionsWindows.cpp
  FuzzerExtraCounters.cpp
  FuzzerExtraCountersDarwin.cpp
  FuzzerExtraCountersWindows.cpp
  FuzzerFork.cpp
  FuzzerIO.cpp
  FuzzerIOPosix.cpp
  FuzzerIOWindows.cpp
  FuzzerLoop.cpp
  FuzzerMerge.cpp
  FuzzerMutate.cpp
  FuzzerSHA1.cpp
  FuzzerTracePC.cpp
  FuzzerUtil.cpp
  FuzzerUtilDarwin.cpp
  FuzzerUtilFuchsia.cpp
  FuzzerUtilLinux.cpp
  FuzzerUtilPosix.cpp
  FuzzerUtilWindows.cpp
  FuzzerInterceptors.cpp
  FuzzerMain.cpp
  FuzzerHFC.cpp
)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_definitions(-DCPPHTTPLIB_NO_EXCEPTIONS)

include_directories(third-party/cpp-httplib)
include_directories(third-party/json/include)

add_library(${PROJECT_NAME} STATIC ${SRC_FILES})

target_include_directories(${PROJECT_NAME}
  PUBLIC
  ${PROJECT_SOURCE_DIR}
)

