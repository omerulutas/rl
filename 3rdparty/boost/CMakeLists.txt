cmake_minimum_required(VERSION 2.8.11)

project(boost)

include(ExternalProject)
include(GNUInstallDirs)

ExternalProject_Add(
	boost
	URL https://dl.bintray.com/boostorg/release/1.73.0/source/boost_1_73_0.7z
	#URL ${CMAKE_CURRENT_SOURCE_DIR}/boost_1_73_0.7z
	URL_MD5 b647977d33441b17e9276ce37309008f
	CONFIGURE_COMMAND ""
	BUILD_COMMAND ""
	BUILD_IN_SOURCE 1
	INSTALL_COMMAND ${CMAKE_COMMAND} -E copy_directory <SOURCE_DIR>/boost ${CMAKE_INSTALL_FULL_INCLUDEDIR}/boost
)
