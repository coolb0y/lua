cmake_minimum_required(VERSION 3.10)
project(lua C)

# ✅ Set output directory for shared libraries (liblua.so)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY
    ${CMAKE_CURRENT_SOURCE_DIR}/../android/.cxx/Debug/2x44o286/arm64-v8a/sysroot/lib)

# ✅ Add the shared library target
add_library(lua SHARED
  lapi.c lauxlib.c lbaselib.c lcode.c
  lcorolib.c
  lctype.c
  ldblib.c ldo.c ldebug.c ldump.c lfunc.c
  lgc.c linit.c liolib.c llex.c lmathlib.c
  lmem.c loadlib.c lobject.c lopcodes.c loslib.c
  lparser.c lstate.c lstring.c lstrlib.c ltable.c
  ltablib.c ltm.c lua.c lundump.c lutf8lib.c
  lvm.c lzio.c
)

# ✅ Make headers accessible to whoever links against this
target_include_directories(lua PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
