package(default_visibility = ["//visibility:public"])

load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_library",
    "go_test",
)

go_test(
    name = "go_default_test",
    srcs = ["certs_test.go"],
    importpath = "k8s.io/kubernetes/cmd/kubeadm/app/phases/certs",
    library = ":go_default_library",
    deps = [
        "//vendor/k8s.io/kubernetes/cmd/kubeadm/app/apis/kubeadm:go_default_library",
        "//vendor/k8s.io/kubernetes/cmd/kubeadm/app/constants:go_default_library",
        "//vendor/k8s.io/kubernetes/cmd/kubeadm/app/phases/certs/pkiutil:go_default_library",
        "//vendor/k8s.io/kubernetes/cmd/kubeadm/test:go_default_library",
        "//vendor/k8s.io/kubernetes/cmd/kubeadm/test/certs:go_default_library",
    ],
)

go_library(
    name = "go_default_library",
    srcs = [
        "certs.go",
        "doc.go",
    ],
    importpath = "k8s.io/kubernetes/cmd/kubeadm/app/phases/certs",
    deps = [
        "//vendor/k8s.io/apimachinery/pkg/util/validation:go_default_library",
        "//vendor/k8s.io/client-go/util/cert:go_default_library",
        "//vendor/k8s.io/kubernetes/cmd/kubeadm/app/apis/kubeadm:go_default_library",
        "//vendor/k8s.io/kubernetes/cmd/kubeadm/app/constants:go_default_library",
        "//vendor/k8s.io/kubernetes/cmd/kubeadm/app/phases/certs/pkiutil:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/registry/core/service/ipallocator:go_default_library",
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
        "//vendor/k8s.io/kubernetes/cmd/kubeadm/app/phases/certs/pkiutil:all-srcs",
    ],
    tags = ["automanaged"],
)
