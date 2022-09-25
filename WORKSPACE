workspace(name = "tf_modules_example")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# Add Terraform rules as repository
TF_MODULES_VERSION="0.0.12"
http_archive(
    name = "tf_modules",
    urls = ["https://github.com/theothertomelliott/bazel-terraform-rules/releases/download/{}/bazel-terraform-rules-{}.tar.gz".format(TF_MODULES_VERSION,TF_MODULES_VERSION)],
    sha256 = "9d001409b79e7e4508011ecabb999d0145cae7ab8dcae23b3f47f09784df48bc",
)
load("@tf_modules//toolchains/terraform:toolchain.bzl", "register_terraform_toolchain")

load("@tf_modules//:deps.bzl", "bazel_terraform_rules_deps")
bazel_terraform_rules_deps()

# Register required Terraform versions
register_terraform_toolchain("1.2.3", default=True)