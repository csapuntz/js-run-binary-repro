load("@aspect_rules_js//js:defs.bzl", "js_run_binary")
load("@npm//:vite/package_json.bzl", vite_bin = "bin")
load("@npm//:defs.bzl", "npm_link_all_packages")

npm_link_all_packages()

vite_bin.vite_binary(
    name = "vite",
    chdir = package_name(),
)

js_run_binary(
    name = "dummy-vite",
    srcs = [
        "index.html",
        #"dummy.js",
    ],
    out_dirs = [
        "bazel-build",
    ],
    args = [
        "build",
        "--outDir=bazel-build/",
    ],
    tool = ":vite",
)
