# Configure example script
SET(FASST_MATLAB_DIR ${CMAKE_BINARY_DIR}/scripts/MATLAB)
CONFIGURE_FILE(CHiME_baseline.m.in ${CMAKE_CURRENT_BINARY_DIR}/CHiME_baseline.m @ONLY)

# Copy VQ.m
CONFIGURE_FILE(VQ.m ${CMAKE_CURRENT_BINARY_DIR} COPYONLY)

# Add to Windows installer
IF(MSVC11)
    SET(FASST_MATLAB_DIR "${CMAKE_INSTALL_PREFIX} ${CPACK_PACKAGE_VERSION}/scripts/MATLAB")
    CONFIGURE_FILE(CHiME_baseline.m.in ${CMAKE_BINARY_DIR}/package/example2/CHiME_baseline.m @ONLY)
    CONFIGURE_FILE(VQ.m ${CMAKE_BINARY_DIR}/package/example2 COPYONLY)
ENDIF()
