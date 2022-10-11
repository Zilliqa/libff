if(${CURVE} STREQUAL "BN128")
  include_directories(ate-pairing/include)

  if (CMAKE_SYSTEM_PROCESSOR MATCHES "(x86)|(X86)|(amd64)|(AMD64)")
    include_directories(xbyak)
    add_library(
      zm
      STATIC

      ate-pairing/src/zm.cpp
      ate-pairing/src/zm2.cpp
    )
  endif()
endif()
