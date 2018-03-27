# Qvik's Swiftlint

*[Qvik](http://qvik.fi/en/)'s official Swiftlint rule set.*

[![Visit Qvik's webpage](http://qvik.fi/wp-content/uploads/2015/02/qvik_logo_black_210x120.png)](http://qvik.fi/en/)

Swiftlint is a tool for enforcing Swift language coding style. The purpose of including it in projects is to produce uniform and clean code across different developers.

For any information on Swiftlint, visit the [Swiftlint homepage](https://github.com/realm/SwiftLint).

## Related Coding style & standard

Follow our [Swift Coding Standard](https://github.com/qvik/swift). Doing so ensures these Swiftlint rules are met.

## Setting up Swiftlint

For detailed installation instructions, see [Swiftlint homepage](https://github.com/realm/SwiftLint). Below are the installation instructions in a nutshell.

### Install Swiftlint via Cocoapods

This is the preferred way of using Swiftlint in your iOS projects; add the following into your `Podfile`:

```sh
  pod 'SwiftLint'
```

Of course, do not forget to run `pod install` after adding this dependency.

### Add `.swiftlint.yml`

Add `.swiftlint.yml` file to your project. This file tells swiftlint your linter configuration. Use the file from this repository. Place this file in the "root" directory of your iOS project, where `.xcodeproj` resides. You do not need to add it into your project.

### Add a run-script phase

Add a "Run Script" step to your target's Build Phases, after the Compile Sources step. Enter this as the sole contents of that script:
```sh
${PODS_ROOT}/SwiftLint/swiftlint
```

That's it! This will run Swiftlint every time you Build, and will cause an error for anyone who hasn't installed Swiftlint. 

