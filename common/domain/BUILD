load("@rules_proto//proto:defs.bzl", "proto_library")

exports_files(["point.proto"])

proto_library(
    name = "point_proto",
    srcs = ["point.proto"],
    strip_import_prefix = "/common",
    visibility = ["//visibility:public"],
    deps = ["@grpc_ecosystem_grpc_gateway//protoc-gen-openapiv2/options:options_proto"],
)

proto_library(
    name = "point_service_proto",
    srcs = ["point_service.proto"],
    strip_import_prefix = "/common",
    visibility = ["//visibility:public"],
    deps = [
        ":point_proto",
        "@com_github_googleapis_googleapis//google/api:annotations_proto",
        "@grpc_ecosystem_grpc_gateway//protoc-gen-openapiv2/options:options_proto",
    ],
)
