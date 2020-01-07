# OpenCV-Help
Tutorials for working with OpenCV
# 1 - Compiling OpenCV with Contrib for Windows
* Download sources for OpenCV 4.1.1 and the OpenCV Contrib 4.1.1 Module. (link: https://github.com/opencv)
* Download and Install CMake (I used 3.16.2)
* Download and Install MinGW (I used mingw-get version 0.6.3 to install mingw).
* After installation open “MinGW Installation Manager” from Start Menu and install Basic->minw32-base-bin. Apply Changes. (it’ll be used by VS 16 2019 for CMake, make sure to add “C:\MinGW\bin\” directory to system environment variables).
* Now you are ready for compilations. Make any changes to OpenCV sources as required.
* Open a CMD or Windows PowerShell in directory containing OpenCV and OpenCV Contrib folders.
* Type “cmake-gui.exe” hit enter.
* In “where is the source code” select the directory “opencv/sources”
* In “where to build binaries” select any location where the final build files will be.
* Press Configure.
  * Select “Visual Studio 16 2019” as generator.
  * Click finish.
  * There will be an error about “python 2.7”, ignore that. Augmented Reality Project doesn’t need OpenCV python build.
  * Keep an active internet connection during configuration process as I’ve noticed that it downloads a few files also.
* Once done. Search for “OPENCV_EXTRA_MODULES_PATH”. Set value to “opencv_contrib/modules” path. (this will add the opencv_contrib sources to CMake configurations.
* Uncheck “BUILD_opencv_python3”.
* Add entry OpenCV_RUNTIME (STRING = vc15)
* You can also add some extra features here like build for cuda etc. (not tested though)
* Press Configure again and once done, press Generate.
* Once done. Navigate to your build directory (in your CMD or PowerShell).
* Type “cmake.exe --build . --config Debug --target INSTALL” and press enter. Now wait as this is going to take about half an hour.
* Done. :D
