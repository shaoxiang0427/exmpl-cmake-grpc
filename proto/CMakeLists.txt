aux_source_directory(./myproto DIR_LIB_SRCS)

include_directories("D:/vs_project/exmpl-cmake-grpc-master/third_party/grpc/include/")
include_directories("D:/vs_project/exmpl-cmake-grpc-master/third_party/protobuf/")

link_directories("D:/vs_project/exmpl-cmake-grpc-master/third_party/grpc/lib/")

add_library(myproto 
				./myproto/address.grpc.pb.cc
				./myproto/address.pb.cc
				./myproto/addressbook.grpc.pb.cc
				./myproto/addressbook.pb.cc
			)
