# yue.nicholas@gmail.com

IF(BUILD_SHARED_LIBS)
    ADD_DEFINITIONS(-DIMATH_EXPORTS)
ENDIF()

SET(IMATH_HEADERS
  ImathBoxAlgo.h
  ImathBox.h
  ImathColorAlgo.h
  ImathColor.h
  ImathEuler.h
  ImathExc.h
  ImathExport.h
  ImathForward.h
  ImathFrame.h
  ImathFrustum.h
  ImathFrustumTest.h
  ImathFun.h
  ImathGL.h
  ImathGLU.h
  # ImathHalfLimits.h
  ImathInt64.h
  ImathInterval.h
  ImathLimits.h
  ImathLineAlgo.h
  ImathLine.h
  ImathMath.h
  ImathMatrixAlgo.h
  ImathMatrix.h
  ImathNamespace.h
  ImathPlane.h
  ImathPlatform.h
  ImathQuat.h
  ImathRandom.h
  ImathRoots.h
  ImathShear.h
  ImathSphere.h
  ImathVecAlgo.h
  ImathVec.h
)

IF(IMATH_USE_HALF)
  list(APPEND IMATH_HEADERS "ImathHalfLimits.h")
ENDIF()

ADD_LIBRARY ( Imath ${LIB_TYPE}
  ImathBox.cpp
  ImathRandom.cpp
  ImathColorAlgo.cpp
  ImathShear.cpp
  ImathFun.cpp
  ImathVec.cpp
  ImathMatrixAlgo.cpp
  ${IMATH_HEADERS}
)

TARGET_LINK_LIBRARIES(Imath Iex)


INSTALL ( TARGETS
  Imath
  DESTINATION
  lib
)

INSTALL ( FILES 
  ${IMATH_HEADERS}
  DESTINATION
  include/OpenEXR
)
