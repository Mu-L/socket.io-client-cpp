include(FetchContent)

FetchContent_Declare(
  Catch2
  GIT_REPOSITORY https://github.com/catchorg/Catch2.git
  GIT_TAG        v3.3.2
)
FetchContent_MakeAvailable(Catch2)

find_package(Threads REQUIRED)

add_executable(sio_test sio_test.cpp)
target_link_libraries(sio_test PRIVATE Catch2::Catch2WithMain sioclient Threads::Threads)
add_test(sioclient_test sio_test)
