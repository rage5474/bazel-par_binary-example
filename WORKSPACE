load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

git_repository(
    name = "subpar",
    remote = "https://github.com/google/subpar",
    tag = "2.0.0",
)

git_repository(
    name = "rules_python",
    remote = "https://github.com/bazelbuild/rules_python.git",
    commit = "748aa53d7701e71101dfd15d800e100f6ff8e5d1"
)

load("@rules_python//python:pip.bzl", "pip3_import")

# Create a central repo that knows about the dependencies needed for
# requirements.txt.
pip3_import(   # or pip3_import
   name = "my_deps",
   requirements = "//:req.txt",
   timeout = 3600,
)

# Load the central repo's install function from its `//:requirements.bzl` file,
# and call it.
load("@my_deps//:requirements.bzl", "pip_install")
pip_install()