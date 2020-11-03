# tilt-example-bazel

[![Build Status](https://circleci.com/gh/tilt-dev/tilt-example-bazel/tree/master.svg?style=shield)](https://circleci.com/gh/tilt-dev/tilt-example-bazel)

An example project that demonstrates setting up a Go/Bazel project in Kubernetes.

This repo will be easier to follow if you're already familiar with Bazel


- [0-base](0-base): The simplest way to start
- [1-measured](1-measured): Use `local_resource` to measure your deployment time
- [2-optimized](2-optimized): Compile Go binaries and copy them into the image.
- [3-recommended](3-recommended): Live-update compiled binaries

## License

Copyright 2020 tilt.dev

Licensed under [the Apache License, Version 2.0](LICENSE)
