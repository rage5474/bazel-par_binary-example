load("@subpar//:subpar.bzl", "par_binary")
load("@my_deps//:requirements.bzl", "requirement")

par_binary(
  name = "app",
  srcs = [
    "app.py",
  ],
  main = "app.py",
  imports = ["."],
  deps = [
    requirement("psutil")
  ],
  visibility = ["//visibility:public"],
)