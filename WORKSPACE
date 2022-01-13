load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "io_tweag_rules_nixpkgs",
    sha256 = "6bedf80d6cb82d3f1876e27f2ff9a2cc814d65f924deba14b49698bb1fb2a7f7",
    strip_prefix = "rules_nixpkgs-a388ab60dea07c3fc182453e89ff1a67c9d3eba6",
    urls = ["https://github.com/tweag/rules_nixpkgs/archive/a388ab60dea07c3fc182453e89ff1a67c9d3eba6.tar.gz"],
)

load("@io_tweag_rules_nixpkgs//nixpkgs:repositories.bzl", "rules_nixpkgs_dependencies")
rules_nixpkgs_dependencies()

load("@io_tweag_rules_nixpkgs//nixpkgs:nixpkgs.bzl", "nixpkgs_python_configure", "nixpkgs_cc_configure", "nixpkgs_git_repository")

nixpkgs_git_repository(
    name = "nixpkgs",
    revision = "17.09", # Any tag or commit hash
    sha256 = "" # optional sha to verify package integrity!
)


nixpkgs_cc_configure(
    name = "nixpkgs_config_cc",
    repository = "@nixpkgs//:default.nix",
)

nixpkgs_python_configure(
    repository = "@nixpkgs//:default.nix",
)
