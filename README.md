# XcodeConcurrentSwiftBuilds

In Xcode 9.2 Apple has introduced another new and experimental feature to accelerate Swift builds. Now Xcode can perform some Swift build tasks in parallel - but only if you turn this feature on yourself.

Quit Xcode and in a Terminal window enter:

`defaults write com.apple.dt.Xcode BuildSystemScheduleInherentlyParallelCommandsExclusively -bool YES`

That will enable experimental concurrent Swift build tasks feature. Relaunch Xcode and build your project. Some projects will see a noticeable difference, but many will not. In informal testing I have seen improvements of up to ~40%. Xcode will use more memory with this feature enabled. If a lack of RAM is slowing down your builds this will not help!

To disable it enter another Terminal command:

`defaults delete com.apple.dt.Xcode BuildSystemScheduleInherentlyParallelCommandsExclusively`

Quit and relaunch Xcode and the feature will be disabled again.