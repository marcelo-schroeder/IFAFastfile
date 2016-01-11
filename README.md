# IFAFastfile
Reusable Fastfile for Fastlane with iOS related development lanes. This Fastfile is ideal for CI servers (my practical experience is with Jenkins).

##How to use it
Firstly, if you don't already have one, create a .env file in the same folder as your Fastfile with the following required environment variables:

```
IFA_XCODE_WORKSPACE=workspace/MyApp.xcworkspace
IFA_XCODE_PROJECT=MyApp/MyApp.xcodeproj
IFA_XCODE_SCHEME=MyApp
IFA_GIT_BRANCH=development
IFA_CHANGELOG=../MyApp/ReleaseNotes.txt
```

Then add the following to the top of your own Fastfile:

	import_from_git(url: 'https://github.com/marcelo-schroeder/IFAFastfile.git')

For further information on the import_from_git action and also how to override lanes, please refer to https://github.com/fastlane/fastlane/blob/master/docs/Advanced.md#importing-another-fastfile
