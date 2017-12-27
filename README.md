# CordovaAndroidLibrary
This is a apache cordova-android + plugins library android project that you can use like dependency to run cordova apps from your native android app

### Dependencies

* This project use [mfdeveloper/android-fat-aar](https://github.com/mfdeveloper/android-fat-aar/tree/aar-module-dependency) (a fork off [adwiv/android-fat-aar](https://github.com/adwiv/android-fat-aar)) that contains custom gradle tasks,
to generate a **`.aar`** file with all _cordova_ android core
dependencies from `cordova.6.2.3-release/framework-release.aar`, + _cordova_ plugins stored in: `cordovapackage/src/main/java`

* Install [Java 8](http://www.oracle.com/technetwork/pt/java/javase/downloads/jdk8-downloads-2133151.html)

## Getting Started

#### Using Android Studio

1. Clone this repo and open this project with [Android Studio](https://developer.android.com/studio/index.html?hl=pt-br)
2. Click on `View > Tool Windows > Gradle` (or click Gradle ![window-gradle](https://developer.android.com/studio/images/buttons/window-gradle.png) in the tool window bar) 
search `:cordovapackage > Tasks > build` and run `assembleRelease` task.
 
    > See [Monitor the build process](https://developer.android.com/studio/run/index.html) documentation
 
    > The **`cordovapackage-release.aar`** file will be generated on: `build/outputs/aar` folder
    
#### Using gradle from command line

1.  and **gradle**
using command below:

```bash
sudo apt-get install gradle
```

2. Into this project path, run the command: (or use **Android Studio**)

```bash
gradle assembleRelease
```

> **PS:** The file **cordovapackage-release.aar** will be generated in: `cordovapackage/build/outputs/aar`
    
3. Import the **`cordovapackage-release.aar`** into your android native project from `File > New Module > Import .JAR/.AAR package`
4. Add this imported module like a dependency on `buil.gradle` like this:

```groovy
    compile project(':my-cordova-library')
```

5. The [cordova-android](https://github.com/apache/cordova-android) core classes + _cordova_ plugins will be allowed to use in your project

## Extra cordova plugins

For while, create a issue or submit a PR with the new _cordova-plugins_ you wish to generate a `.aar` file 
with this. In future, the extra plugins can be added more dinamically :)


### Authors

Michel Felipe <michel.ferreira@serpro.gov.br>