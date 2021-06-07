load("//rules/protoc-gen-openapiv2:defs.bzl", "protoc_gen_openapiv2")
load("@rules_proto//proto:defs.bzl", "proto_library")

proto_library(
    name = "service_proto",
    srcs = ["service.proto"],
    deps = [
        ":bar_proto",
        "@com_github_googleapis_googleapis//google/api:annotations_proto",
        "@grpc_ecosystem_grpc_gateway//protoc-gen-openapiv2/options:options_proto",
    ],
)

proto_library(
    name = "bar_proto",
    srcs = [
        "bar.proto",
    ],
    deps = [
        "@grpc_ecosystem_grpc_gateway//protoc-gen-openapiv2/options:options_proto",
    ],
)

proto_library(
    name = "api_proto",
    srcs = [
        "api.proto",
    ],
    deps = [
        "//common/domain:point_proto",
        "@grpc_ecosystem_grpc_gateway//protoc-gen-openapiv2/options:options_proto",
    ],
)

protoc_gen_openapiv2(
    name = "openapi",
    proto = [
        ":api_proto",
        ":service_proto",
        "//common/domain:point_service_proto",
    ],
    single_output = True,
)
