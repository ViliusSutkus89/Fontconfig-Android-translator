# CMakeLists.txt
#
# Fontconfig-Android-translator (https://github.com/ViliusSutkus89/Fontconfig-Android-translator)
#
# Copyright (c) 2019,2020 Vilius Sutkus <ViliusSutkus89@gmail.com>
#
# This program is free software: you can redistribute it and/or modify
# it under the terms of the GNU General Public License version 3 as
# published by the Free Software Foundation.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program.  If not, see <https://www.gnu.org/licenses/>.

cmake_minimum_required(VERSION 3.10.2 FATAL_ERROR)
set(CMAKE_BUILD_TYPE Release CACHE STRING "Build configuration (Debug, Release, RelWithDebInfo, MinSizeRel)")

project(Fontconfig-Android-translator-test)

# @TODO: enable
if (CMAKE_BUILD_TYPE STREQUAL "Debug" AND FALSE)
    add_library(TranslatorInstrumentedTests SHARED TranslatorInstrumentedTests.cc)
endif()
