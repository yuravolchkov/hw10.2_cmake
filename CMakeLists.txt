# CMakeList.txt: проект CMake для hw10.2Cmake; включите исходный код и определения,
# укажите здесь логику для конкретного проекта.
#
cmake_minimum_required (VERSION 3.20)

# Включение горячей перезагрузки для компиляторов MSVC, если поддерживается.
if (POLICY CMP0141)
  cmake_policy(SET CMP0141 NEW)
  set(CMAKE_MSVC_DEBUG_INFORMATION_FORMAT "$<IF:$<AND:$<C_COMPILER_ID:MSVC>,$<CXX_COMPILER_ID:MSVC>>,$<$<CONFIG:Debug,RelWithDebInfo>:EditAndContinue>,$<$<CONFIG:Debug,RelWithDebInfo>:ProgramDatabase>>")
endif()

project ("hw10.2Cmake")

# Добавьте источник в исполняемый файл этого проекта.
add_executable (hw10.2Cmake "hw6.3.cpp" "00FigSource.cpp" "00PrintInfo.cpp" "10TriSource.cpp" "11RTriSource.cpp" "12ITriSource.cpp" "13ETriSource.cpp" "20QuaSource.cpp" "21RecSource.cpp" "22SquSource.cpp" "23ParSource.cpp" "24RhoSource.cpp")

if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET hw10.2Cmake PROPERTY CXX_STANDARD 20)
endif()

# TODO: Добавьте тесты и целевые объекты, если это необходимо.
