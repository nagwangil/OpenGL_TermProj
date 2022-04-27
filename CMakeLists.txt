CMAKE_MINIMUM_REQUIRED ( VERSION 3.0.0 )
# 프로젝트 이름 및 버전
PROJECT ( "study" )
# 빌드 대상 바이너리 파일명 및 소스파일 목록
SET ( OUTPUT_ELF
        "OpenGl_TermProj.out"
        )
SET ( SRC_FILES
        "./study.cpp"
        )

# 공통 컴파일러
SET ( CMAKE_CXX_COMPILER "clang++" )

find_package(OpenGL REQUIRED)

set(GLUT_LIBRARIES libglut.3.dylib)
set(GLUT_INCLUDE_DIRS /opt/homebrew/Cellar/freeglut/3.2.2/include)
set(GLUT_LIBRARY_DIRS /opt/homebrew/Cellar/freeglut/3.2.2/lib)

set(GLM_LIBRARIES libglut.3.dylib)
set(GLM_INCLUDE_DIRS /opt/homebrew/Cellar/glm/0.9.9.8/include)
set(GLM_LIBRARY_DIRS /opt/homebrew/Cellar/glm/0.9.9.8/lib)

set(GLFW_LIBRARIES libglfw.3.dylib)
set(GLFW_INCLUDE_DIRS /opt/homebrew/Cellar/glfw/3.3.6/include)
set(GLFW_LIBRARY_DIRS /opt/homebrew/Cellar/glfw/3.3.6/lib)

INCLUDE_DIRECTORIES ( ${OPENGL_INCLUDE_DIRS} ${GLUT_INCLUDE_DIRS} ${GLM_INCLUDE_DIRS} ${GLFW_INCLUDE_DIRS} )
ADD_COMPILE_OPTIONS ( "-g" )

LINK_LIBRARIES( ${OPENGL_LIBRARIES} ${GLUT_LIBRARIES}  ${GLFW_LIBRARIES})

LINK_DIRECTORIES ( ${OPENGL_LIBRARY_DIRS} ${GLUT_LIBRARY_DIRS} ${GLFW_LIBRARY_DIRS} )

ADD_EXECUTABLE( ${OUTPUT_ELF} ${SRC_FILES} )