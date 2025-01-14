[![Build and Test - Fixed Dependencies](https://github.com/faaxm/exmpl-cmake-grpc/actions/workflows/build.yml/badge.svg)](https://github.com/faaxm/exmpl-cmake-grpc/actions/workflows/build.yml)

[![Build and Test - Latest Dependencies](https://github.com/faaxm/exmpl-cmake-grpc/actions/workflows/build-latest-deps.yml/badge.svg)](https://github.com/faaxm/exmpl-cmake-grpc/actions/workflows/build-latest-deps.yml) (might indicate a bug in dependencies)

# Protobuf/GRPC with CMake Example

This is a basic example of a CMake project using Protobuf together with gRPC in C++.

For some background info, have a look at this blog post explaining [how to structure gRPC projects with CMake](https://www.f-ax.de/dev/2020/11/08/grpc-plugin-cmake-support.html).

### gRPC Reflection
Reflection can be enabled by linking agains `gRPC::grpc++_reflection`, enabling support for the `grpc_cli` tool.

If this project is linked with a static version of the grpc library from vcpkg
the `-Wl,--whole-archive` flag has to be used. (together with `--allow-multiple-definition`). When linking dynamically,
you will want to link the reflection library with `--no-as-needed`.



关联grpc库操作指南：
1、protoc --grpc_out=.\ --plugin=protoc-gen-grpc="grpc_cpp_plugin.exe" ./addressbook.proto          protoc --cpp_out=.\address.proto    生成对应的文件
2、下载https://github.com/grpc/grpc库，需要用管理员权限打开VS，编译“INSTALL”项目，会在C:\Program Files\grpc生成对应的include头文件、lib库、dll库等；                                       3、使用本项目还需要关联protobuf库下的google文件夹的头文件
