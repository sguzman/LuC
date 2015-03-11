cmake_minimum_required(VERSION 3.1)
project(lua C)

IF(EXISTS ${/usr/bin/clang})
  set(CMAKE_C_COMPILER             "/usr/bin/clang")
  set(CMAKE_AR      "/usr/bin/llvm-ar")
  #set(CMAKE_LINKER  "/usr/bin/llvm-ld")
  set(CMAKE_NM      "/usr/bin/llvm-nm")
  set(CMAKE_OBJDUMP "/usr/bin/llvm-objdump")
  set(CMAKE_RANLIB  "/usr/bin/llvm-ranlib")
ENDIF()


file(GLOB helloworld_SRC
"src/lapi.c"
"src/lcode.c"
"src/lctype.c"
"src/ldebug.c"
"src/ldo.c"
"src/ldump.c"
"src/lfunc.c"
"src/lgc.c"
"src/llex.c"
"src/lmem.c"
"src/lobject.c"
"src/lopcodes.c"
"src/lparser.c"
"src/lstate.c"
"src/lstring.c"
"src/ltable.c"
"src/ltm.c"
"src/lundump.c"
"src/lvm.c"
"src/lzio.c"
"src/lauxlib.c"
"src/lbaselib.c"
"src/lbitlib.c"
"src/lcorolib.c"
"src/ldblib.c"
"src/liolib.c"
"src/lmathlib.c"
"src/loslib.c"
"src/lstrlib.c"
"src/ltablib.c"
"src/lutf8lib.c"
"src/loadlib.c"
"src/linit.c"
)

add_executable(lua src/lua.c ${helloworld_SRC})
target_link_libraries(lua m)

