cmake_minimum_required(VERSION 2.8)
project(asyncweb)
find_package(qibuild)

include_directories( "." "include" )

qi_create_lib( asyncweb
  SRC src/http_server.cpp
      src/http_connection.cpp
      src/http_request_parser.cpp
      src/http_reply.cpp
      src/http_request_handler.cpp
      src/websocket_connection.cpp
      src/websocket_request_handler.cpp
      src/websocket_message.cpp
      src/http_request.cpp
  SHARED
)

qi_install_header( include/async_web_server_cpp/*.hpp SUBFOLDER async_web_server_cpp  )

qi_use_lib(asyncweb boost openssl)
qi_stage_lib(asyncweb)
