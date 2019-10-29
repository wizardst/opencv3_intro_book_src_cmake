
# 当个cpp文件的完整路径
FILE(GLOB SIG_SRC "${CMAKE_CURRENT_SOURCE_DIR}/*.cpp")

# 以当个文件名为PROJNAME
string(REGEX REPLACE ".*/(.*).cpp" \\1 PROJNAME ${SIG_SRC})

# 使用替换的方式获取PROJNAME
#set(current_dir ${CMAKE_CURRENT_SOURCE_DIR})
#string(REPLACE ${current_dir}/ "" PROJNAME ${SIG_SRC})
#STRING(REPLACE ".cpp" "" PROJNAME ${PROJNAME})


aux_source_directory(. SRC_LIST)

add_executable(${PROJNAME} ${SRC_LIST})
target_link_libraries(${PROJNAME} ${OpenCV_LIBS})

