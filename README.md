# IFAFastfile
Reusable Fastfile for Fastlane with iOS related development lanes. This Fastfile is ideal for CI servers (tested with Jenkins, Bamboo and Bitrise).

This Fastfile automates:

* iOS app releases.
 * Native support for Testflight but it can be integrated with other distribution systems such as HockeyApp.
 * Both Developer and Enterprise accounts supported via Fastlane configuration.
* Open source project releases to Github.
 * Native support for iOS frameworks but it can be extended to other types of projects.
 * Integrated Cocoapods trunk releases.
 * Support for GitHub release notes.

It also supports:

* Automated release tagging using Git tags.
* Optional dependency management using Cocoapods but it can be used with any other dependency manager.

##How to use it
Firstly, if you don't already have one, create a .env file in the same folder as your Fastfile with the following environment variables (these apply to both apps and frameworks):

```
IFA_XCODE_WORKSPACE=workspace/MyApp.xcworkspace
IFA_XCODE_PROJECT=MyApp/MyApp.xcodeproj
IFA_XCODE_SCHEME=MyApp
IFA_GIT_BRANCH=development
IFA_CHANGELOG=../MyApp/ReleaseNotes.txt
```
If you maintain an open source project on GitHub, please also add the following to the .env file:

```
IFA_GITHUB_REPOSITORY=github-user/MyProject
```

Then import IFAFastfile at the top of your own Fastfile like so:

	import_from_git(url: 'https://github.com/marcelo-schroeder/IFAFastfile.git')

The above does a checkout of IFAFastfile directly from Git, but you can also keep it as part of your project (e.g. using a Git submodule) for better performance using Fastlane's import action.

You can now run the following to get help on the available lanes:

```
fastlane lanes
```

For further information on the import_from_git and import actions, and also how to override lanes, please refer to https://github.com/fastlane/fastlane/blob/master/docs/Advanced.md#importing-another-fastfile
