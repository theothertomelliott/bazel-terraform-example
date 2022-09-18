workspace(name = "tf_modules_example")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# Skylib dependency required for Terraform rules
http_archive(
    name = "bazel_skylib",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/bazel-skylib/releases/download/1.2.1/bazel-skylib-1.2.1.tar.gz",
        "https://github.com/bazelbuild/bazel-skylib/releases/download/1.2.1/bazel-skylib-1.2.1.tar.gz",
    ],
    sha256 = "f7be3474d42aae265405a592bb7da8e171919d74c16f082a5457840f06054728",
)
load("@bazel_skylib//:workspace.bzl", "bazel_skylib_workspace")
bazel_skylib_workspace()

# Add Terraform rules as repository
TF_MODULES_VERSION="0.0.9"
http_archive(
    name = "tf_modules",
    urls = ["https://github.com/theothertomelliott/bazel-terraform-rules/archive/refs/tags/{}.tar.gz".format(TF_MODULES_VERSION)],
    sha256 = "428a26f7ca392e57ae3fbcba3dd0d2f48bc93e9127062ff5980a6ba9c2ff5af7",
    strip_prefix = "bazel-terraform-rules-{}".format(TF_MODULES_VERSION),
)
load("@tf_modules//toolchains/terraform:toolchain.bzl", "register_terraform_toolchain")

# Register required Terraform versions
register_terraform_toolchain("1.2.3", default=True)