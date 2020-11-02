### How to build wxWidgets 3.1.4 on macOSX 12 newer

1. Download wxWidgets 3.1.4 from official site
2. build and install wxWidgets
   
            #### a. sudo cmake -G "Unix Makefiles" ~/Downloads/wxWidgets-3.1.4/ -DwxBUILD_SHARED=OFF -DCMAKE_INSTALL_PREFIX=/opt/wxWidgets/3.1.4  
            #### b. sudo cmake --build . --target install  

3. use wx-config located in $PREFIX/bin to list the CXXFLAGS for your compiler and LIBS for your linker.
4. Add corresponding options in your CMakeLists.

Have a fun!