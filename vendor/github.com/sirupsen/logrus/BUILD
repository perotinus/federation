load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "alt_exit.go",
        "doc.go",
        "entry.go",
        "exported.go",
        "formatter.go",
        "hooks.go",
        "json_formatter.go",
        "logger.go",
        "logrus.go",
        "text_formatter.go",
        "writer.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:darwin_amd64": [
            "terminal_bsd.go",
        ],
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "terminal_linux.go",
        ],
        "//conditions:default": [],
    }),
    importpath = "github.com/sirupsen/logrus",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/golang.org/x/crypto/ssh/terminal:go_default_library",
    ] + select({
        "@io_bazel_rules_go//go/platform:darwin_amd64": [
            "//vendor/golang.org/x/sys/unix:go_default_library",
        ],
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "//vendor/golang.org/x/sys/unix:go_default_library",
        ],
        "//conditions:default": [],
    }),
)

go_test(
    name = "go_default_test",
    srcs = [
        "alt_exit_test.go",
        "entry_test.go",
        "formatter_bench_test.go",
        "hook_test.go",
        "json_formatter_test.go",
        "logger_bench_test.go",
        "logrus_test.go",
        "text_formatter_test.go",
    ],
    importpath = "github.com/sirupsen/logrus",
    library = ":go_default_library",
    deps = ["//vendor/github.com/stretchr/testify/assert:go_default_library"],
)

go_test(
    name = "go_default_xtest",
    srcs = [
        "example_basic_test.go",
        "example_hook_test.go",
    ],
    importpath = "github.com/sirupsen/logrus_test",
    deps = [
        ":go_default_library",
        "//vendor/gopkg.in/gemnasium/logrus-airbrake-hook.v2:go_default_library",
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
        "//vendor/github.com/sirupsen/logrus/hooks/syslog:all-srcs",
        "//vendor/github.com/sirupsen/logrus/hooks/test:all-srcs",
    ],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
