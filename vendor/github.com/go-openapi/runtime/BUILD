load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "bytestream.go",
        "client_auth_info.go",
        "client_operation.go",
        "client_request.go",
        "client_response.go",
        "constants.go",
        "discard.go",
        "headers.go",
        "interfaces.go",
        "json.go",
        "request.go",
        "statuses.go",
        "text.go",
        "values.go",
        "xml.go",
    ],
    importpath = "github.com/go-openapi/runtime",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/go-openapi/errors:go_default_library",
        "//vendor/github.com/go-openapi/strfmt:go_default_library",
        "//vendor/github.com/go-openapi/swag:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = [
        "authinfo_test.go",
        "bytestream_test.go",
        "client_request_test.go",
        "client_response_test.go",
        "headers_test.go",
        "json_test.go",
        "request_test.go",
        "text_test.go",
        "xml_test.go",
    ],
    importpath = "github.com/go-openapi/runtime",
    library = ":go_default_library",
    deps = [
        "//vendor/github.com/go-openapi/errors:go_default_library",
        "//vendor/github.com/go-openapi/strfmt:go_default_library",
        "//vendor/github.com/stretchr/testify/assert:go_default_library",
    ],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [
        ":package-srcs",
        "//vendor/github.com/go-openapi/runtime/client:all-srcs",
        "//vendor/github.com/go-openapi/runtime/internal/testing:all-srcs",
        "//vendor/github.com/go-openapi/runtime/middleware:all-srcs",
        "//vendor/github.com/go-openapi/runtime/security:all-srcs",
        "//vendor/github.com/go-openapi/runtime/yamlpc:all-srcs",
    ],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
