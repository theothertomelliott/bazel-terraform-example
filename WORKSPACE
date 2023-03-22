workspace(name = "tf_modules_example")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# Add Terraform rules as repository
http_archive(
    name = "tf_modules",
    urls = ["https://github.com/theothertomelliott/bazel-terraform-rules/releases/download/0.1.0/bazel-terraform-rules-0.1.0.tar.gz"],
    sha256 = "dd57306f8ea2417e9c91ee4dddeb7f7f8e1c986d937634a207ecbc5bb3f40869",
)
load("@tf_modules//toolchains/terraform:toolchain.bzl", "register_terraform_toolchain")

load("@tf_modules//:deps.bzl", "bazel_terraform_rules_deps")
bazel_terraform_rules_deps()

# Register required Terraform versions
register_terraform_toolchain("1.2.3", default=True)