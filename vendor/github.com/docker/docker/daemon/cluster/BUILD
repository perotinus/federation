load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "cluster.go",
        "configs.go",
        "filters.go",
        "helpers.go",
        "listen_addr.go",
        "listen_addr_others.go",
        "networks.go",
        "noderunner.go",
        "nodes.go",
        "secrets.go",
        "services.go",
        "swarm.go",
        "tasks.go",
        "utils.go",
    ] + select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "listen_addr_linux.go",
        ],
        "//conditions:default": [],
    }),
    importpath = "github.com/docker/docker/daemon/cluster",
    visibility = ["//visibility:public"],
    deps = [
        "//vendor/github.com/docker/distribution/reference:go_default_library",
        "//vendor/github.com/docker/docker/api/errors:go_default_library",
        "//vendor/github.com/docker/docker/api/types:go_default_library",
        "//vendor/github.com/docker/docker/api/types/backend:go_default_library",
        "//vendor/github.com/docker/docker/api/types/filters:go_default_library",
        "//vendor/github.com/docker/docker/api/types/network:go_default_library",
        "//vendor/github.com/docker/docker/api/types/swarm:go_default_library",
        "//vendor/github.com/docker/docker/api/types/time:go_default_library",
        "//vendor/github.com/docker/docker/daemon/cluster/controllers/plugin:go_default_library",
        "//vendor/github.com/docker/docker/daemon/cluster/convert:go_default_library",
        "//vendor/github.com/docker/docker/daemon/cluster/executor:go_default_library",
        "//vendor/github.com/docker/docker/daemon/cluster/executor/container:go_default_library",
        "//vendor/github.com/docker/docker/opts:go_default_library",
        "//vendor/github.com/docker/docker/pkg/ioutils:go_default_library",
        "//vendor/github.com/docker/docker/pkg/signal:go_default_library",
        "//vendor/github.com/docker/docker/runconfig:go_default_library",
        "//vendor/github.com/docker/docker/runconfig/opts:go_default_library",
        "//vendor/github.com/docker/libnetwork/cluster:go_default_library",
        "//vendor/github.com/docker/swarmkit/api:go_default_library",
        "//vendor/github.com/docker/swarmkit/manager/encryption:go_default_library",
        "//vendor/github.com/docker/swarmkit/node:go_default_library",
        "//vendor/github.com/gogo/protobuf/types:go_default_library",
        "//vendor/github.com/pkg/errors:go_default_library",
        "//vendor/github.com/sirupsen/logrus:go_default_library",
        "//vendor/golang.org/x/net/context:go_default_library",
        "//vendor/google.golang.org/grpc:go_default_library",
    ] + select({
        "@io_bazel_rules_go//go/platform:linux_amd64": [
            "//vendor/github.com/vishvananda/netlink:go_default_library",
        ],
        "//conditions:default": [],
    }),
)

go_test(
    name = "go_default_test",
    srcs = ["filters_test.go"],
    importpath = "github.com/docker/docker/daemon/cluster",
    library = ":go_default_library",
    deps = ["//vendor/github.com/docker/docker/api/types/filters:go_default_library"],
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
        "//vendor/github.com/docker/docker/daemon/cluster/controllers/plugin:all-srcs",
        "//vendor/github.com/docker/docker/daemon/cluster/convert:all-srcs",
        "//vendor/github.com/docker/docker/daemon/cluster/executor:all-srcs",
        "//vendor/github.com/docker/docker/daemon/cluster/provider:all-srcs",
    ],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
