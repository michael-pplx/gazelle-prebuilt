# Prebuilt Gazelle

[Gazelle](https://github.com/bazelbuild/bazel-gazelle) is a tool for generating BUILD files for Bazel or compatible build systems.

## Why?

Gazelle is commonly built from source on developer's machines, using a Go toolchain.
However this doesn't always work well.

Here's a representative take:

https://plaid.com/blog/hello-bazel/

> A week later, reports started coming in from users complaining that running the tool was taking too long, sometimes multiple minutes. This took us by surprise – the team had not encountered any slowness in the 6 months leading up to that moment, and the generation was only taking a handful of seconds in CI. Once we added instrumentation to our tooling, we were surprised to find a median duration of about 20 seconds and a p95 duration extending to several minutes.

Not only can it be slow, it can often be broken. That's because Gazelle extensions don't have to be written in pure Go. As an example, the Python extension depends on a C library called TreeSitter, which forces projects to setup a functional and hermetic cc toolchain.

https://github.com/bazel-contrib/rules_python/issues/1913
