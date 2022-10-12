---
layout: page
title: What's New
include_in_header: true
---

# Release Notes

## [1.0.2] - 2022-10-09

### Added
- Added links to learning material videos in Projects Browser for both project setup & add translation best practices.

### Fixed
- Fixed an issue with the app icon switcher not updating in Projects Browser + added a hint on setting icon failure.
- Fixed an issue where the limits check wouldn't work properly on first config file open.
- Fixed an issue with the build script not pointing to the home directory properly, making the build script not recognize the CLI tool.


## [1.0.1] - 2022-10-07

### Added
- New 'Help' menu item with a direct link to leave a rating on the App Store.

### Fixed
- Fixed an issue where no error details would be presented when enum generation failed in project setup, getting stuck in the process.


## [1.0.0] - 2022-10-05

### Added
- Updated DeepL supported languages to include Indonesian, Turkish, and Ukrainian.

### Changed
- Improved the "Add Translation" window completion experience by hiding app and switching to Xcode rather than quitting.

### Fixed
- Fixed an issue where no error details would be presented when counting keys in config file failed.


## [1.0.0-beta.4] - 2022-09-20

### Added
- Added "Show Projects Browser" & "Show Add Translation" buttons to "Window" menu bar to help with some window management issues.
- Added a new option to configure if an empty line should be placed between every two keys in a `.strings` file or not.

### Changed
- Reverted Add Translation window to quit the entire app again on Cancel or Insert button press to prevent duplicate windows.
- The list of supported languages in source language selection dropdowns is now sorted alphabetically.
- Improved automatic detection of multiple subpaths on setup and adding `/` suffix to folders for less confusion.
- Improved performance of application in several places by preventing unnecessary re-computes of SwiftUI views.

### Deprecated
- The `.remafox` config file structure has received new `appleStringsFilesConfig` options. An automatic migration is available (only in this beta release!) – just open all your config files once and save them right away to upgrade.

### Fixed
- Fixed an issue with machine-translation not finding `.strings(dict)` files when the language forlders are in same path as `.remafox` config file. (Thanks to [Ulf](https://twitter.com/vieuxrenard))
- Fixed an issue that could lead to a crash during machine-translation with `.strings(dict)` files in `.lproj` paths with invalid lang codes.
- Fixed an issue in the project browser that could delete the wrong project in the list after confirming the delete.
- Fixed an issue where editing a `.stringsdict` file from Xcode would lead to a different indentation format than when produced by ReMafoX.
- Fixed an issue that rendered some leftover SF Symbols in Add Translation text views incorrectly.
- Fixed an issue with multi-line translation values in the source language leading to compiler errors in the generated Swift file.


## [1.0.0-beta.3] - 2022-09-01

### Added
- A new App Icon Switcher in the app's settings allows users to select their preferred app icon design & color.
- A new `remafox translate` subcommand in the CLI tool completes the build script by adding a machine-translation step. (Thanks to [Ulf](https://twitter.com/vieuxrenard))
- Added sound effects on a few specific success or error actions, such as project setup completion or occurrence of an error.
- A new option in the app's settings for turning off app sound effects for users who prefer no sound effects.
- A new error message with a helpful text is shown on pressing a project in browser when the config file was moved. (Thanks to [Nico](https://twitter.com/n1c0_muc)!)

### Changed
- Improved relevance of web searches of users by changing error code separator from '-' to 'x'.
- Simplified the wording of Help menu entries to a shorter & more familiar terminology.
- Changed the temporary app icon to the final design after [2 Twitter surveys](https://twitter.com/Remafox_App).
- Improved setup for developers opening a pre-configured project: The open panel should now always show the right project root path.
- Moved 'Copy code' button into the code box for a more intuitive place to find it. (Thanks to [Nico](https://twitter.com/n1c0_muc)!)
- Adjusted color of multi-steps tutorial page controls to look less like a clickable button. (Thanks to [Nico](https://twitter.com/n1c0_muc)!)
- Changed the app accent color from a greenish color to be more blue, based on the new default app icon. (Thanks to [Nico](https://twitter.com/n1c0_muc)!)

### Deprecated
- The `.remafox` config file structure has received a new `configFilePath` field. An automatic migration is available (only in this beta release!) – just open all your config files once and save them right away to upgrade.

### Removed
- Removed extra emphasis on "Resources Enum File Path" text field in config file to simplify information hierarchy. (Thanks to [Nico](https://twitter.com/n1c0_muc)!)

### Fixed
- Fixed an issue where the machine translation would be executed before normalization, leading to the possibility of temporarily untranslated keys. (Thanks to [Ulf](https://twitter.com/vieuxrenard))
- Fixed an issue which prevented the machine translation results view from being shown when started from config file. (Thanks to [Ulf](https://twitter.com/vieuxrenard))
- Fixed an issue that could lead to a crash in some language combinations within the smart mapping logic when translating pluralized Strings.
- Fixed the build script showing an invalid relative path to the config file by calculating relative path from project if available. (Thanks to [Ulf](https://twitter.com/vieuxrenard))
- Fixed an issue where the build script could fail with an `Error Code: RWF-X` stating 'data couldn't be read because it is missing' even if it wasn't. [#3](https://github.com/FlineDev/ReMafoX/issues/3) (Thanks to [Vasiliy](https://twitter.com/anivaros))
- Fixed an issue that could prevent a translation text field receiving user input from the user after pressing 'Rescan' button in add translation view.
- Fixed an issue with jumping to a next language text field via pressing 'tab' on pluralized text entry in add translation view.
- Fixed an issue that prevented the default indentation style for new projects to be '4 spaces' (it defaulted to '3 spaces' instead).
- Fixed an issue that rendered SF Symbols in text views incorrectly.
- Fixed an issue where special characters in machine-translated texts would not be correctly escaped in `.strings` files, leading to a build error.
- Fixed an issue which could lead to a crash on project setup in projects with Base-localized Storyboard/XIB files.


## [1.0.0-beta.2] - 2022-07-24

### Added
- Warns when config file format has higher version than currently supported with hint to upgrade.
- Added automatic search for Xcode projects and a picker to select one. This helps detect the supported languages more reliably. (Thanks to [Holger](https://twitter.com/_holger)!)

### Changed
- Improved formatting of Xcode integration instructions.
- Widened click area for expandable disclosure groups (such as 'Show Explanation') from triangle to full title. (Thanks to [Ulf](https://twitter.com/vieuxrenard))
- Changed the title of diclosure groups to state 'Hide' instead of 'Show' when they are in expanded state.
- Made the settings window size smaller to fit the currently small amount of options.
- The add translation window no longer quits the entire app but hides all windows instead on Cancel or Insert button press.
- Changed recommended 'Add translation' shortcut to ⌥⌘L from ⌥L which is used for '@' in common keyboard layouts like German.
- Changed the 'Copy' button title to 'Copy Code' to make it clear what is being copied in Build Script walkthrough. (Thanks to [Nico](https://twitter.com/n1c0_muc)!)
- Hidden detailed explanation behind disclosure group in last step of Build Script walkthrough for less text. (Thanks to [Nico](https://twitter.com/n1c0_muc)!)

### Removed
- Removed potentially confusing different doc sample language setting, always using source language now.
- Removed the "New" item menu bar entries & window tabbing support to prevent confusion with window management.
- Removed the need to specify if the provided DeepL auth key is for a Free or a Pro plan. Auto-detecting based on key instead.

### Fixed
- Removed SF Symbol icons that were not showing properly for the about menu entry and help menu entries.
- Fixed an issue with Strings(dict) files not being updated on search path changes after initial setup.
- Fixed an issue where a non-existent Strings(dict) file could be selected by default in add translation window.
- Fixed an issue with source language chooser being empty when localized files are placed at projects root. (Thanks to [Ulf](https://twitter.com/vieuxrenard)!)
- Fixed an issue where contents from Storyboard/XIB-related Strings files would be included into the generated resources enum.


## [1.0.0-beta.1] - 2022-07-07

### List of Features in this Beta
- **Add new localizable Strings** to your Strings files without ever leaving your Swift file in Xcode (Free)
- **Machine-translate** your localizations to all ~40 languages [supported also by iOS](https://www.apple.com/ios/feature-availability/#system-language-system-language) using Microsoft or DeepL services (Free, but services not included)
- **Safely access** translations in code using **generated Swift enums** for auto-completion & compiler checks (Free)
- **Lint** your Strings files for empty translations or duplicate keys and show **in-line warnings** in Xcode (Free)
- **Incrementally update** your base-localized Storyboard's or XIB's related Strings files (Free)
- **Normalize** your Strings by sorting keys alphabetically & harmonizing with a selected source language (Free)
- Easily **add new pluralized** localizable Strings to your Stringsdict files without leaving Xcode (Paid)
- Easily **machine-translate pluralized** localizable Strings with smart language-rules-aware pluralization counts (Paid)

### Improvements over BartyCrouch
- A **new config file format** which can be edited with an intuitive **visual editor** (no `.bartycrouch.toml` file needed)
- A new **"Preview matching files" button** to conveniently simulate a files search & adjust paths accordingly based on results
- An explanation for every single configurable option for more confidence in adjusting the config to your needs
- A **built-in SwiftUI-compatible enum generator** with lots of customization options (no need for SwiftGen for Strings)
- The API keys for machine translations services are no longer stored in the config file (no secrets in Git)
- A **built-in project scanner** to provide smarter defaults for a quick start – including a BartyCrouch migrator (read-only)
- Multiple **built-in step-by-step guides** for easier integration with Xcode
- Adding new localizations **no longer breaks Xcodes edit history** thanks to a built-in Xcode Source Editor extension

### Planned for the Future
- Easy way to send translations to translators & integrate their provided translations
- Synchronize translations between Android & iOS platforms of the same app
- Provide a glossary of reviewed common Strings (to improve machine-translated apps)
- UI/Unit tests integration to provide context screenshots for keys for translators
- ... and much more!
