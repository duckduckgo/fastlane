# fastlane

This repository is a fork of [fastlane](https://github.com/fastlane/fastlane) with a fix for https://github.com/fastlane/fastlane/pull/21472.
See original README at [README.md](/README.md).

## Versioning and Relases

While `master` branch is kept 1:1 up to date with upstream, releases are done directly from upstream tags,
after cherry-picking [the top of `dominik/upload-metadata-fix` branch](https://github.com/duckduckgo/fastlane/commit/58157000bbc2a8a041d6f69b9b15ba748ef9887c). Versions follow upstream versioning, just with a `+ddg` "version metadata",
e.g. `2.214.0+ddg`.

### Usage

Replace your existing `fastlane` entry in Gemfile with the following line
(adjusting version as needed):

```ruby
gem 'fastlane', :git => 'https://github.com/duckduckgo/fastlane.git', :tag => '2.214.0+ddg'
```

### Release process:

To make a new release:
1. Fetch from upstream including tags: `git fetch --tags upstream`.
2. Check out the latest upstream tag, e.g. `2.214.0`.
3. Branch out of that tag into `release/<upstream_tag>+ddg` branch.
4. Cherry-pick the fix commit on top of that branch: `git cherry-pick dominik/upload-metadata-fix`.
5. Tag the branch with `<upstream_tag>+ddg` tag.
6. Push the branch and the tag to this repository.

## Contributions

We do not accept contributions to this repository at this time. However, feel free to open an issue in order to start a discussion.

