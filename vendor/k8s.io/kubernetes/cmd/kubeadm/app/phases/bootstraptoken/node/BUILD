package(default_visibility = ["//visibility:public"])

load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_library",
    "go_test",
)

go_test(
    name = "go_default_test",
    srcs = ["token_test.go"],
    importpath = "k8s.io/kubernetes/cmd/kubeadm/app/phases/bootstraptoken/node",
    library = ":go_default_library",
    deps = ["//vendor/k8s.io/kubernetes/cmd/kubeadm/app/apis/kubeadm:go_default_library"],
)

go_library(
    name = "go_default_library",
    srcs = [
        "tlsbootstrap.go",
        "token.go",
    ],
    importpath = "k8s.io/kubernetes/cmd/kubeadm/app/phases/bootstraptoken/node",
    deps = [
        "//vendor/k8s.io/api/core/v1:go_default_library",
        "//vendor/k8s.io/api/rbac/v1:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/api/errors:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/apis/meta/v1:go_default_library",
        "//vendor/k8s.io/client-go/kubernetes:go_default_library",
        "//vendor/k8s.io/kubernetes/cmd/kubeadm/app/constants:go_default_library",
        "//vendor/k8s.io/kubernetes/cmd/kubeadm/app/util/apiclient:go_default_library",
        "//vendor/k8s.io/kubernetes/cmd/kubeadm/app/util/token:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/bootstrap/api:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/util/version:go_default_library",
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
)
