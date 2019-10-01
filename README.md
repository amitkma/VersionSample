# Versioning Sample
This project is intended to showcase the scripting needed to do semantic versioning with proper handling of branch and constraints while following the gitflow model.

## How to Use
To use this in your android app, you need to do the following steps. 
- Add these three variables into your app module level `build.gradle` file ie. `app/build.gradle`
```groovy
// Manifest version information!
def versionMajor = 1
def versionMinor = 0
def versionPatch = 0
```
- Next, change the `versionName` and `versionCode` inside android block of `app/build.gradle`
```groovy
android {
    defaultConfig {
        ---------
        versionCode versionMajor * 10000 + versionMinor * 1000 + versionPatch * 100 // you can use any other formula too.
        versionName "${versionMajor}.${versionMinor}.${versionPatch}" // Semantic Version.
        ---------
        ---------
        // other configurations
    }
}
```
- Use `bump-version.sh` to change the version number depending on the changes that you have done.

That's it. 

> Keep in my mind that those scripts are meant to support proper gitflow but you can customise those scripts to suite your own git flow. To read more about Git-flow which is supported by `bump-version.sh` and `tag-version.sh`, Kindly checkout this - [GiflowAndVersioning.md](/GitflowAndVersioning.md)