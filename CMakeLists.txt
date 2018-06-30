CMAKE_MINIMUM_REQUIRED(VERSION 3.5)

PROJECT ( ObjectOrientedGraphicsLibrary )

SET (CMAKE_CXX_STANDARD 11)

INCLUDE_DIRECTORIES (
  ${CMAKE_SOURCE_DIR}/src
  include
  )

SET ( OOGL_SRCS
  src/GL/Math/Mat3.cpp
  src/GL/Math/Mat4.cpp
  src/GL/Math/Vec2.cpp
  src/GL/Math/Vec3.cpp
  src/GL/Math/Vec4.cpp
  src/GL/Window/Window.cpp
  src/GL/Window/Window_X11.cpp
  src/GL/GL/Extensions.cpp
  src/GL/GL/Context.cpp
  src/GL/GL/Context_X11.cpp
  src/GL/GL/Shader.cpp
  src/GL/GL/Program.cpp
  src/GL/GL/VertexBuffer.cpp
  src/GL/GL/VertexArray.cpp
  src/GL/GL/Texture.cpp
  src/GL/GL/Renderbuffer.cpp
  src/GL/GL/Framebuffer.cpp
  src/GL/Util/Image.cpp
  src/GL/Util/Mesh.cpp
)

SET ( JPEG_SRCS
  src/GL/Util/libjpeg/jcarith.c
  src/GL/Util/libjpeg/jidctfst.c
  src/GL/Util/libjpeg/jfdctint.c
  src/GL/Util/libjpeg/jccolor.c
  src/GL/Util/libjpeg/jcmarker.c
  src/GL/Util/libjpeg/jaricom.c
  src/GL/Util/libjpeg/jquant1.c
  src/GL/Util/libjpeg/jctrans.c
  src/GL/Util/libjpeg/jdmainct.c
  src/GL/Util/libjpeg/jdsample.c
  src/GL/Util/libjpeg/jchuff.c
  src/GL/Util/libjpeg/jdhuff.c
  src/GL/Util/libjpeg/jcomapi.c
  src/GL/Util/libjpeg/jmemnobs.c
  src/GL/Util/libjpeg/jdtrans.c
  src/GL/Util/libjpeg/jdapistd.c
  src/GL/Util/libjpeg/jdarith.c
  src/GL/Util/libjpeg/jcparam.c
  src/GL/Util/libjpeg/jdcolor.c
  src/GL/Util/libjpeg/jcapimin.c
  src/GL/Util/libjpeg/jcmaster.c
  src/GL/Util/libjpeg/jfdctfst.c
  src/GL/Util/libjpeg/jdmarker.c
  src/GL/Util/libjpeg/jfdctflt.c
  src/GL/Util/libjpeg/jcdctmgr.c
  src/GL/Util/libjpeg/jutils.c
  src/GL/Util/libjpeg/jccoefct.c
  src/GL/Util/libjpeg/jcinit.c
  src/GL/Util/libjpeg/jdinput.c
  src/GL/Util/libjpeg/jerror.c
  src/GL/Util/libjpeg/jdcoefct.c
  src/GL/Util/libjpeg/jquant2.c
  src/GL/Util/libjpeg/jidctint.c
  src/GL/Util/libjpeg/jddctmgr.c
  src/GL/Util/libjpeg/jdpostct.c
  src/GL/Util/libjpeg/jcmainct.c
  src/GL/Util/libjpeg/jdapimin.c
  src/GL/Util/libjpeg/jcprepct.c
  src/GL/Util/libjpeg/jidctflt.c
  src/GL/Util/libjpeg/jdmaster.c
  src/GL/Util/libjpeg/jdatasrc.c
  src/GL/Util/libjpeg/jdatadst.c
  src/GL/Util/libjpeg/jmemmgr.c
  src/GL/Util/libjpeg/jcsample.c
  src/GL/Util/libjpeg/jdmerge.c
  src/GL/Util/libjpeg/jcapistd.c
  src/GL/Util/libpng/pngrutil.c
  src/GL/Util/libpng/pngwutil.c
  src/GL/Util/libpng/pngwtran.c
  src/GL/Util/libpng/pngmem.c
  src/GL/Util/libpng/pngrio.c
  src/GL/Util/libpng/pngtrans.c
  src/GL/Util/libpng/pngvcrd.c
  src/GL/Util/libpng/pngwio.c
  src/GL/Util/libpng/png.c
  src/GL/Util/libpng/pnggccrd.c
  src/GL/Util/libpng/pngerror.c
  src/GL/Util/libpng/pngrtran.c
  src/GL/Util/libpng/pngwrite.c
  src/GL/Util/libpng/pngset.c
  src/GL/Util/libpng/pngpread.c
  src/GL/Util/libpng/pngread.c
  src/GL/Util/libpng/pngget.c
  src/GL/Util/zlib/deflate.c
  src/GL/Util/zlib/uncompr.c
  src/GL/Util/zlib/zutil.c
  src/GL/Util/zlib/inffast.c
  src/GL/Util/zlib/adler32.c
  src/GL/Util/zlib/inflate.c
  src/GL/Util/zlib/trees.c
  src/GL/Util/zlib/crc32.c
  src/GL/Util/zlib/inftrees.c
  src/GL/Util/zlib/compress.c
  )

ADD_LIBRARY ( OOGL STATIC
  ${OOGL_SRCS}
  ${JPEG_SRCS}
  )

ADD_SUBDIRECTORY ( samples )

INSTALL ( TARGETS
  OOGL
  DESTINATION
  lib
  )

INSTALL ( DIRECTORY
  include/GL/GL
  include/GL/Math
  include/GL/Util
  include/GL/Window
  DESTINATION
  include
  )

INSTALL ( FILES
  include/GL/OOGL.hpp
  include/GL/Platform.hpp
  DESTINATION
  include
  )
