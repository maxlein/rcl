This document is a declaration of software quality for the `rcl` package, based on the guidelines in [REP-2004](https://www.ros.org/reps/rep-2004.html).

# `rcl` Quality Declaration

The package `rcl` claims to be in the **Quality Level 4** category.

Below are the rationales, notes, and caveats for this claim, organized by each requirement listed in the [Package Quality Categories in REP-2004](https://index.ros.org/doc/ros2/Contributing/Developer-Guide/#package-quality-categories).

## Version Policy [1]

### Version Scheme [1.i]

`rcl` uses `semver` according to the recommendation for ROS Core packages in the [ROS 2 Developer Guide](https://index.ros.org/doc/ros2/Contributing/Developer-Guide/#versioning).

### Version Stability [1.ii]

`rcl` is not at a stable version, i.e. `>= 1.0.0`.

### Public API Declaration [1.iii]

All symbols in the installed headers are considered part of the public API.

All installed headers are in the [`include`](./include/rcl) directory of the package, headers in any other folders are not installed and considered private.

### API Stability Policy [1.iv]

`rcl` will not break public API within a released ROS distribution, i.e. no major releases once the ROS distribution is released.

### ABI Stability Policy [1.v]

`rcl` contains C code and therefore must be concerned with ABI stability, and will maintain ABI stability within a ROS distribution.

### ABI and ABI Stability Within a Released ROS Distribution [1.vi]

`rcl` will not break API nor ABI within a released ROS distribution, i.e. no major releases once the ROS distribution is released.

## Change Control Process [2]

### Change Requests [2.i]

All changes will occur through a pull request, check the [ROS 2 Developer Guide](https://index.ros.org/doc/ros2/Contributing/Developer-Guide/#change-control-process) for additional information.

### Contributor Origin [2.ii]

This package uses DCO as its confirmation of contributor origin policy. More information can be found in [CONTRIBUTING](../CONTRIBUTING.md).

### Peer Review Policy [2.iii]

All pull requests will be peer-reviewed, check [ROS 2 Developer Guide](https://index.ros.org/doc/ros2/Contributing/Developer-Guide/#change-control-process) for additional information.

### Continuous Integration [2.iv]

All pull requests must pass CI on all [tier 1 platforms](https://www.ros.org/reps/rep-2000.html#support-tiers).

Currently nightly results can be seen here:
* [linux-aarch64_release](https://ci.ros2.org/view/nightly/job/nightly_linux-aarch64_release/lastBuild/testReport/rcl/)
* [linux_release](https://ci.ros2.org/view/nightly/job/nightly_linux_release/lastBuild/testReport/rcl/)
* [mac_osx_release](https://ci.ros2.org/view/nightly/job/nightly_osx_release/lastBuild/testReport/rcl/)
* [windows_release](https://ci.ros2.org/view/nightly/job/nightly_win_rel/lastBuild/testReport/rcl/)

###  Documentation Policy [2.v]

All pull requests must resolve related documentation changes before merging.

## Documentation [3]

### Feature Documentation [3.i]

`rcl` provides the main elements of its API listed using doxygen. Refer to the [ROS2 concepts](https://index.ros.org/doc/ros2/Concepts/) and [ROS2 Client Libraries](https://index.ros.org/doc/ros2/Concepts/ROS-2-Client-Libraries/) pages for reference of elements covered by this package.

### Public API Documentation [3.ii]

`rcl` has embedded API documentation and it is generated using doxygen. Currently, its eloquent version is hosted [here](http://docs.ros2.org/eloquent/api/rcl/). Latest version has to be generated before considering this item fully resolved.

New additions to the public API require documentation before being added.

### License [3.iii]

The license for `rcl` is Apache 2.0, and a summary is in each source file, the type is declared in the [`package.xml`](./package.xml) manifest file, and a full copy of the license is in the [`LICENSE`](../LICENSE) file.

There is an automated test which runs a linter that ensures each file has a license statement. [Here](https://ci.ros2.org/view/nightly/job/nightly_linux_release/lastBuild/testReport/rcl/) can be found a list with the latest results of the various linters being run on the package.

### Copyright Statements [3.iv]

The copyright holders each provide a statement of copyright in each source code file in `rcl`.

There is an automated test which runs a linter that ensures each file has at least one copyright statement. Latest linter result report can be seen [Here](https://ci.ros2.org/view/nightly/job/nightly_linux_release/lastBuild/testReport/rcl/copyright/).

## Testing [4]

### Feature Testing [4.i]

Most features in `rcl` have corresponding tests which simulate typical usage, and they are located in the [`test`](./test) directory.
New features are required to have tests before being added.
Currently nightly test results can be seen here:
* [linux-aarch64_release](https://ci.ros2.org/view/nightly/job/nightly_linux-aarch64_release/lastBuild/testReport/rcl/)
* [linux_release](https://ci.ros2.org/view/nightly/job/nightly_linux_release/lastBuild/testReport/rcl/)
* [mac_osx_release](https://ci.ros2.org/view/nightly/job/nightly_osx_release/lastBuild/testReport/rcl/)
* [windows_release](https://ci.ros2.org/view/nightly/job/nightly_win_rel/lastBuild/testReport/rcl/)

### Public API Testing [4.ii]

Most of the functionality of the declared API in this package is covered in its unit tests. Currently it has a line coverage of [77%](https://ci.ros2.org/job/ci_linux_coverage/85/cobertura/src_ros2_rcl_rcl_src_rcl/).

### Coverage [4.iii]

`rcl` follows the recommendations for ROS Core packages in the [ROS 2 Developer Guide](https://index.ros.org/doc/ros2/Contributing/Developer-Guide/#code-coverage), and opts to use line coverage instead of branch coverage.

This includes:

- tracking and reporting line coverage statistics
- no lines are manually skipped in coverage calculations

Changes are required to make a best effort to keep or increase coverage before being accepted, but decreases are allowed if properly justified and accepted by reviewers.

Current coverage statistics can be viewed (77%) [here](https://ci.ros2.org/job/ci_linux_coverage/85/cobertura/src_ros2_rcl_rcl_src_rcl/). Current coverage statistics need to be improved to reach a higher quality level.

### Performance [4.iv]

`rcl` does not conduct performance tests.

### Linters and Static Analysis [4.v]

`rcl` uses and passes all the ROS2 standard linters and static analysis tools for a C++ package as described in the [ROS 2 Developer Guide](https://index.ros.org/doc/ros2/Contributing/Developer-Guide/#linters-and-static-analysis). Passing implies there are no linter/static errors when testing against CI of supported platforms.

Currently nightly test results can be seen here:
* [linux-aarch64_release](https://ci.ros2.org/view/nightly/job/nightly_linux-aarch64_release/lastBuild/testReport/rcl/)
* [linux_release](https://ci.ros2.org/view/nightly/job/nightly_linux_release/lastBuild/testReport/rcl/)
* [mac_osx_release](https://ci.ros2.org/view/nightly/job/nightly_osx_release/lastBuild/testReport/rcl/)
* [windows_release](https://ci.ros2.org/view/nightly/job/nightly_win_rel/lastBuild/testReport/rcl/)

## Dependencies [5]

Below are evaluations of each of `rcl`'s run-time and build-time dependencies that have been determined to influence the quality.

It has several "buildtool" dependencies, which do not affect the resulting quality of the package, because they do not contribute to the public library API.
It also has several test dependencies, which do not affect the resulting quality of the package, because they are only used to build and run the test code.

### Direct Runtime ROS Dependencies [5.i]

#### `rmw`

The `rmw` package provides the API used by `rcl` to interact with the underlying middleware in an abstract way.

It is **Quality Level 4**, see its [Quality Declaration document](https://github.com/ros2/rmw/rmw/QUALITY_DECLARATION.md).

#### `rcl_interfaces`

The `rcl_interfaces` package provides some common ROS Message and ROS Service types which are used to implement certain client library features.

It is **Quality Level 4**, see its [Quality Declaration document](https://github.com/ros2/rcl_interfaces/blob/master/rcl_interfaces/QUALITY_DECLARATION.md).

#### `rcl_logging_spdlog`

The `rcl_logging_spdlog` package provides the default logging implementation by wrapping the `spdlog` library.

It is **Quality Level 4**, see its [Quality Declaration document](https://github.com/ros2/rcl_logging/rcl_logging_spdlog/Quality_Declaration.md).

#### `rcl_yaml_param_parser`

The `rcl_yaml_param_parser` package provides an API that is used to parse YAML configuration files which may be used to configure ROS and specific nodes.

It is **Quality Level 4**, see its [Quality Declaration document](https://github.com/ros2/rcl/tree/master/rcl_yaml_param_parser/Quality_Declaration.md).

#### `rcutils`

The `rcutils` package provides an API which contains common utilities and data structures needed when programming in C.

It is **Quality Level 4**, see its [Quality Declaration document](https://github.com/ros2/rcutils/blob/master/QUALITY_DECLARATION.md).

#### `rmw_implementation`

The `rmw_implementation` package provides access to the default rmw implementation, and provides the ability to dynamically switch rmw implementations if more than one is available.

It is **Quality Level 4**, see its [Quality Declaration document](https://github.com/ros2/rmw_implementation/blob/master/QUALITY_DECLARATION.md).

#### `rosidl_runtime_c`

The `rosidl_runtime_c` package provides runtime interfaces in C based on user defined ROS Messages and ROS Services, as well as associated support functions for those types.

It is **Quality Level 4**, see its [Quality Declaration document](https://github.com/ros2/rosidl/tree/master/rosidl_runtime_c/Quality_Declaration.md).

#### `tracetools`

The `tracetools` package provides utilities for instrumenting the code in `rcl` so that it may be traced for debugging and performance analysis.

It is **Quality Level 4**, see its [Quality Declaration document](https://gitlab.com/micro-ROS/ros_tracing/ros2_tracing/-/blob/master/tracetools/QUALITY_DECLARATION.md).

### Optional Direct Runtime ROS Dependencies [5.ii]

`rcl` has no optional Direct Runtime ROS dependencies that need to be considered for this declaration.

### Direct Runtime non-ROS Dependency [5.iii]

`rcl` has no Direct Runtime non-ROS dependencies that need to be considered for this declaration.

## Platform Support [6]

`rcl` supports all of the tier 1 platforms as described in [REP-2000](https://www.ros.org/reps/rep-2000.html#support-tiers), and tests each change against all of them.

## Security [7]

### Vulnerability Disclosure Policy [7.i]

`rcl` does not have a Vulnerability Disclosure Policy.

# Current status Summary

The chart below compares the requirements in the REP-2004 with the current state of the `rcl` package.

|Number| Requirement| Current state |
|--|--|--|
|1| **Version policy** |---|
|1.i|Version Policy available | ✓ |
|1.ii|Stable version |☓|
|1.iii|Declared public API|✓|
|1.iv|API stability policy|✓|
|1.v|ABI stability policy|✓|
|1.vi_|API/ABI stable within ros distribution|✓|
|2| **Change control process** |---|
|2.i| All changes occur on change request | ✓|
|2.ii| Contributor origin (DCO, CLA, etc) | ✓|
|2.iii| Peer review policy | ✓ |
|2.iv| CI policy for change requests | ✓ |
|2.v| Documentation policy for change requests | ✓ |
|3| **Documentation** | --- |
|3.i| Per feature documentation | ☓ |
|3.ii| Per public API item documentation | * |
|3.iii| Declared License(s) | ✓ |
|3.iv| Copyright in source files| ✓ |
|3.v.a| Quality declaration linked to README | ✓ |
|3.v.b| Centralized declaration available for peer review |✓|
|4| Testing | --- |
|4.i| Feature items tests | ✓ |
|4.ii| Public API tests | ✓ |
|4.iii.a| Using coverage | * |
|4.iii.a| Coverage policy | ✓ |
|4.iv.a| Performance tests (if applicable) | ☓ |
|4.iv.b| Performance tests policy| ✓ |
|4.v.a| Code style enforcement (linters)| ✓ |
|4.v.b| Use of static analysis tools | ✓ |
|5| Dependencies | --- |
|5.i| Must not have ROS lower level dependencies | ✓ |
|5.ii| Optional ROS lower level dependencies| ✓ |
|5.iii| Justifies quality use of non-ROS dependencies |✓|
|6| Platform support | --- |
|6.i| Support targets Tier1 ROS platforms| ✓ |
|7| Security | --- |
|7.i| Vulnerability Disclosure Policy | ☓ |
