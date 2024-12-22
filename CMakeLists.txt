cmake_minimum_required(VERSION 3.26)

project(TTC)

set(CMAKE_CXX_STANDARD 20)

add_executable(
    ${PROJECT_NAME}
    src/main.cpp
    src/fpscounter.cpp
    src/board.cpp
    src/player.cpp
    src/text.cpp
    src/drawing.cpp
    src/bot.cpp
    src/menu.cpp
    src/game.cpp
)

target_include_directories(${PROJECT_NAME} PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/headers)

# include and link SFML
target_include_directories(${PROJECT_NAME} PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/SFML/include)
target_link_directories(${PROJECT_NAME} PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/SFML/lib)
target_link_libraries(${PROJECT_NAME} mingw32 sfml-system sfml-window sfml-graphics sfml-audio)

file(COPY assets DESTINATION ${CMAKE_BINARY_DIR})