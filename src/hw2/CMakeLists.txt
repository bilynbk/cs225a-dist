# create an executable
ADD_EXECUTABLE (hw2 hw2.cpp)

# and link the library against the executable
TARGET_LINK_LIBRARIES (hw2
        ${CS225A_COMMON_LIBRARIES})

# export resources such as model files.
# NOTE: this requires an install build
SET(RESOURCE_DIR ${CS225A_BINARY_DIR}/resources)
FILE(MAKE_DIRECTORY ${RESOURCE_DIR})
SET(APP_RESOURCE_DIR ${RESOURCE_DIR}/hw2)
FILE(MAKE_DIRECTORY ${APP_RESOURCE_DIR})
FILE(COPY kuka_iiwa.urdf world.urdf DESTINATION ${APP_RESOURCE_DIR})
