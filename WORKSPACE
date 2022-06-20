workspace(name = "tf_modules_example")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

TF_MODULES_VERSION="0.0.3"
http_archive(
    name = "tf_modules",
    urls = ["https://github.com/theothertomelliott/bazel-terraform-rules/archive/refs/tags/{}.tar.gz".format(TF_MODULES_VERSION)],
    sha256 = "dfb9e22c7d80956261a76c477dfc256e8dc92047d3225caceb3e8264e7966c8a",
    strip_prefix = "bazel-terraform-rules-{}".format(TF_MODULES_VERSION),
)

load("@tf_modules//toolchains/terraform:toolchain.bzl", "register_terraform_toolchain")

register_terraform_toolchain("1.2.3", default=True)