CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

PROJECT(RendererVisitor)

SET(RENDERERVISITOR_HEADERS
Color.h
Vertex.h
Shape.h
Rectangle.h
Triangle.h
Renderer.h
OpenGLRenderer.h
DirectXRenderer.h
ConsoleRenderer.h
)

SET(RENDERERVISITOR_SOURCES
Color.cpp
Vertex.cpp
Shape.cpp
Rectangle.cpp
Triangle.cpp
OpenGLRenderer.cpp
DirectXRenderer.cpp
ConsoleRenderer.cpp
main.cpp
)

FIND_PACKAGE(OpenGL REQUIRED)
FIND_PACKAGE(GLUT REQUIRED)

SOURCE_GROUP("Header Files" FILES ${RENDERERVISITOR_HEADERS})
SOURCE_GROUP("Source Files" FILES ${RENDERERVISITOR_SOURCES})

INCLUDE_DIRECTORIES(
${OPENGL_INCLUDE_DIRS}
${GLUT_INCLUDE_DIRS}
)

ADD_EXECUTABLE(RendererVisitor ${RENDERERVISITOR_HEADERS} ${RENDERERVISITOR_SOURCES})

TARGET_LINK_LIBRARIES(RendererVisitor 
${OPENGL_LIBRARIES}
${GLUT_LIBRARY}
d3d9
ddraw 
dinput8 
dxguid  
)