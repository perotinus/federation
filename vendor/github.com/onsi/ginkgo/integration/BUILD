load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = ["integration.go"],
    importpath = "github.com/onsi/ginkgo/integration",
    visibility = ["//visibility:public"],
)

go_test(
    name = "go_default_xtest",
    srcs = [
        "convert_test.go",
        "coverage_test.go",
        "fail_test.go",
        "flags_test.go",
        "integration_suite_test.go",
        "interrupt_test.go",
        "precompiled_test.go",
        "progress_test.go",
        "run_test.go",
        "skip_test.go",
        "subcommand_test.go",
        "suite_command_test.go",
        "suite_setup_test.go",
        "tags_test.go",
        "test_description_test.go",
        "verbose_and_succinct_test.go",
        "watch_test.go",
    ],
    importpath = "github.com/onsi/ginkgo/integration_test",
    deps = [
        "//vendor/github.com/onsi/ginkgo:go_default_library",
        "//vendor/github.com/onsi/ginkgo/types:go_default_library",
        "//vendor/github.com/onsi/gomega:go_default_library",
        "//vendor/github.com/onsi/gomega/gbytes:go_default_library",
        "//vendor/github.com/onsi/gomega/gexec:go_default_library",
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
    srcs = [":package-srcs"],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
