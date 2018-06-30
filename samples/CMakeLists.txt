SET ( REQUIRED_LINK_LIBRARIES
  OOGL
  X11
  Xrandr
  GL
  )

ADD_EXECUTABLE ( Triangle
  Triangle/main.cpp
  )

TARGET_LINK_LIBRARIES ( Triangle
  ${REQUIRED_LINK_LIBRARIES}
  )

ADD_EXECUTABLE ( StencilReflection
  StencilReflection/main.cpp
  )
TARGET_LINK_LIBRARIES ( StencilReflection
  ${REQUIRED_LINK_LIBRARIES}
  )

ADD_EXECUTABLE ( ShadowMapping
  ShadowMapping/main.cpp
  )
TARGET_LINK_LIBRARIES ( ShadowMapping
  ${REQUIRED_LINK_LIBRARIES}
  )


ADD_EXECUTABLE ( TransformFeedback
  TransformFeedback/main.cpp
  )
TARGET_LINK_LIBRARIES ( TransformFeedback
  ${REQUIRED_LINK_LIBRARIES}
  )

INSTALL ( TARGETS
  Triangle
  StencilReflection
  ShadowMapping
  TransformFeedback
  DESTINATION
  bin
  )

INSTALL ( FILES
  # StencilReflection required files
  StencilReflection/tank.obj
  StencilReflection/platform.obj
  StencilReflection/tank.jpg
  StencilReflection/platform.png
  # ShadowMapping required files
  ShadowMapping/scene.obj
  ShadowMapping/scene.png
  DESTINATION
  bin
  )
