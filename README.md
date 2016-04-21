# Qvik's Swiftlint

*[Qvik](http://qvik.fi/en/)'s official Swiftlint rule set.*

[![Visit Qvik's webpage](http://qvik.fi/wp-content/uploads/2015/02/qvik_logo_black_210x120.png)](http://qvik.fi/en/)

For any information on Swiftlint, visit the [Swiftlint homepage](https://github.com/realm/SwiftLint).

## Related Coding style & standard

Follow our [Swift Coding Standard](https://github.com/qvik/swift). Doing so ensures these Swiftlint rules are met.

## Setting up Swiftlint

For detailed installation instructions, see [Swiftlint homepage](https://github.com/realm/SwiftLint). Below are the installation instructions in a nutshell.

1. Homebrew is used to install Swiftlint. If you dont have Homebrew, install it as such:
```sh
 /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
2. Install Swiftlint
```sh
brew update
brew install swiftlint
```
If Homebrew complains about errors while linking swiftlint, make sure your `/usr/local` is writable by you. A clean way to make it so is to issue such command: 
```sh
sudo chown -R `whoami`:admin /usr/local
```
3. Add .swiftlint.yml file to your project. This file tells swiftlint your linter configuration. Use the file from this repository. Place this file in the "root" directory of your iOS project, where `.xcodeproj` resides.
4. Add a "Run Script" step to your target's Build Phases, after the Compile Sources step, as such:
```sh
if which swiftlint >/dev/null; then
swiftlint
else
echo "error: Swiftlint not installed - see https://github.com/realm/SwiftLint"
exit 1
fi
```
This will run Swiftlint every time you Build, and will cause an error for anyone who hasn't installed Swiftlint. 

