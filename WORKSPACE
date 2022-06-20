workspace(name = "tf_modules_example")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

TF_MODULES_VERSION="0.0.2"
http_archive(
    name = "tf_modules",
    urls = ["https://github.com/theothertomelliott/bazel-terraform-rules/archive/refs/tags/{}.tar.gz".format(TF_MODULES_VERSION)],
    sha256 = "905b5f68c5cc15dfb72a99dcc2fbb2dde6bfebce6932b7957f3fd602f897082a",
    strip_prefix = "bazel-terraform-rules-{}".format(TF_MODULES_VERSION),
)

load("@tf_modules//toolchains/terraform:toolchain.bzl", "register_terraform_toolchain")

register_terraform_toolchain("1.2.3", default=True)