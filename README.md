# Oh My Git! - Apple Silicon fix

An unofficial build of [Oh My Git!](https://github.com/git-learning-game/oh-my-git) with one fix for Apple Silicon Macs.

**The problem.** The macOS build of the game is made for Intel, so on an Apple Silicon Mac it runs under Rosetta, and so does every command the game starts. Players report that the game closes when a level starts ([upstream issue #193](https://github.com/git-learning-game/oh-my-git/issues/193) collects these reports).

**The fix.** When the game detects that it runs under Rosetta, it starts its shell natively (`arch -arm64`). Only `scenes/shell.gd` changes. The pull request to the original game is [#254](https://github.com/git-learning-game/oh-my-git/pull/254).

**Tested** on a MacBook Pro with an M1 Pro. Not tested on other chips. Intel Macs are not affected by the change. Windows and Linux builds are not included.

## Install

1. Download `oh-my-git-apple-silicon-fix-macos.zip` from [Releases](../../releases/latest) and unpack it.
2. The app is not signed, so macOS blocks it on the first launch. Open System Settings → Privacy & Security, scroll down to Security, press Open Anyway and confirm. In the terminal, `xattr -cr "/Applications/Oh My Git!.app"` has the same effect.
3. The game needs Git on your Mac. `git --version` in the terminal tells you if you have it.

The game is in English. A version with the same fix in nine more languages is in [oh-my-git-translation](https://github.com/teohanki/oh-my-git-translation).

Found a problem? Write in [Issues](../../issues).

## License and credits

The game is by bleeptrack and blinry, with music by winniehell. The fix is by Teo Hanki. Everything is under the [Blue Oak Model License 1.0.0](LICENSE.md), the same license as the original.
