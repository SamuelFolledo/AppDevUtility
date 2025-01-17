# Strings Utility

<p>
  <a>
    <a href="https://goreportcard.com/badge/github.com/SamuelFolledo/StringsUtility" />
    <img alt="commits" src="https://goreportcard.com/badge/github.com/SamuelFolledo/StringsUtility" target="_blank" />
    <a href="https://github.com/SamuelFolledo/StringsUtility/commits/master">
    <img alt="commits" src="https://img.shields.io/github/commit-activity/w/SamuelFolledo/StringsUtility?color=green" target="_blank" />
  </a> 
  <a href="#" target="_blank">
    <img alt="License: MIT" src="https://img.shields.io/badge/License-MIT-yellow.svg" />
  </a>
  <a href="https://github.com/imthaghost/gitmoji-changelog">
    <img src="https://img.shields.io/badge/changelog-gitmoji-brightgreen.svg" alt="gitmoji-changelog">
  </a>
</p>

Swift utility written in [Go](https://golang.org/) which automates boring [Swift strings](https://developer.apple.com/documentation/swift/string) tasks like:
- <ins>**Feature 1: Constantify Strings**</ins> Creates global constant variables from all .swift files to a constant file
- <ins>**Feature 2: Localize Strings**</ins> Transform all valid translatable strings as [NSLocalizedString](https://developer.apple.com/documentation/foundation/nslocalizedstring) and copies them to all ```Localizable.strings``` files while avoiding duplicated strings
- <ins>**Feature 3: Translate Strings**</ins> Uses [Google Cloud Translation](https://cloud.google.com/translate/docs) to automatically translate all strings in all ```Localizable.strings```, allowing iOS, MacOS, etc apps to support multiple languages in a few seconds

<p align="center">
    <img src="https://github.com/SamuelFolledo/StringsUtility/blob/master/static/logo/StringsUtilityMinLogo.png" width="450" height="327"
    >
</p>

## Live Demo
<p align="center">
    <img src="https://github.com/SamuelFolledo/StringsUtility/blob/master/static/gifs/StringsUtilityLiveDemo.gif" width="900" height="506"
    >
</p>

### Why Use?
- Avoid unintended typos
- Have strings autocompleted
- Easily manage all your strings in one file
- Auto generate strings ```Localizable.strings``` and avoid duplicate strings
- Automatically translate all strings in ```Localizable.strings```

## How to Use?
### Download StringsUtility
-  clone the repo
  ```
  $ git clone https://github.com/SamuelFolledo/StringsUtility
  $ cd StringsUtility
  ```

### [Install Golang](https://sourabhbajaj.com/mac-setup/Go/README.html) with Updated Homebrew:
-  Make sure HomeBrew is updated
  ```
  $ brew update
  $ brew install golang
  ```

### [Setup Google Cloud Translator](https://cloud.google.com/translate/docs/basic/setup-basic): *Required for feature 3 only*
-  [Set up a Cloud Console project](https://cloud.google.com/translate/docs/basic/setup-basic)
-  Download a private key as JSON
-  While inside StringsUtility directory, run in terminal once
  ```
  $ go get -u cloud.google.com/go/translate
  ```
-  **Important:** Run this command **once** each fresh terminal. Replace the ```[PATH]``` to the path of the ```.json``` file downloaded from setup 2 step 3. [Instructions](https://cloud.google.com/docs/authentication/production) for more info or for Windows setup
    ```
    export GOOGLE_APPLICATION_CREDENTIALS=[PATH]
    ```
    For example:
    ```
    export GOOGLE_APPLICATION_CREDENTIALS=/Users/Samuel/Downloads/StringsUtility-Tester-785c7f11aedf.json
    ```

For further details, tips, recommendations go to [Tips and Requirements](Tips.md)

### Run StringsUtility
- run the program locally replacing ```[PATH_TO_YOUR_PROJECT]``` with your project directory
  ```
  $ go build && go run main.go -dir=[PATH_TO_YOUR_PROJECT]
  ``` 
  For example:
  ```
  go build && go run main.go -dir=/Users/macbookpro15/Desktop/StringsUtilityTester
  ```

-----

## [Tips and Requirements](Tips.md):
- Currently does not support multi line strings
- To avoid unnecessary translation, strings which contains substrings like file extensions, keywords, and symbols **will not be translated**. Edit strings and files to follow these standards.
  ```
  "/", "\\", "{", "}", "_", "#", "%", ".swift", ".xib", ".storyboard", ".jpg", ".jpeg", ".png", ".mp4", ".mp3", ".wav", ".mov", ".gif", "http", "https", ".com", "identifier"
  ```
- Strings like url, identifiers, and more which contains substrings like the following **will not be constantify**.
  ```
  "/", "\\", "{", "}", "http", "https", ".com", "#", "%", "identifier"
  ```
- [Suported Languages](https://github.com/SamuelFolledo/StringsUtility/blob/master/Tips.md#languages-currently-supported)

*For more tips and requirements click [here](https://github.com/SamuelFolledo/StringsUtility/blob/master/Tips.md#tips)*


### Links
- My final project for [MakeSchool](makeschool.com)'s [BEW2.5: Patterns & Practices in Strongly Typed Languages](https://make-school-courses.github.io/BEW-2.5-Strongly-Typed-Languages/#/) - the only university that teaches Go
- [MakeUtility Requirements](https://github.com/Make-School-Courses/BEW-2.5-Strongly-Typed-Languages/blob/master/Project/MakeUtility.md)
- My article: [5 Steps to Localizing your Swift Apps](https://medium.com/@samuelfolledo/5-steps-to-localizing-your-swift-apps-36c76e9700f7)
- Added feature 2 and 3 during [Make School's Spring Intensive 1.3](https://github.com/Make-School-Courses/INT-1.3-AND-INT-2.3-Spring-Intensive)
- Follow me at [LinkedIn](https://www.linkedin.com/in/samuel-folledo/), [GitHub](https://github.com/SamuelFolledo) and [Portfolio](https://www.makeschool.com/portfolio/SamuelFolledo)

##### To have a customized version for your company standards, feel free to email me at <samuelfolledo@gmail.com>

Lincense under [MIT License](LICENSE)
