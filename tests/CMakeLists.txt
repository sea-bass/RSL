list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)

find_package(Catch2 3.1.0 REQUIRED)
find_package(range-v3 0.11.0 REQUIRED)

add_executable(test-rsl
    monad.cpp
    no_discard.cpp
    overload.cpp
    queue.cpp
    random.cpp
    try.cpp)
target_link_libraries(test-rsl PRIVATE
    rsl::rsl
    Catch2::Catch2WithMain
    range-v3::range-v3
)
catch_discover_tests(test-rsl)
