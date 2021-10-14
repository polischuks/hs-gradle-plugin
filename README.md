# hs-gradle-plugin

It is a gradle plugin to manage versions for Hyperskill projects

## Usage

To use the plugin, include in your build script:

```gradle
buildscript {
    repositories {
        mavenCentral()
        maven {
            url 'https://jitpack.io'
        }
    }
    
    dependencies {
        classpath "com.github.hyperskill:hs-gradle-plugin:release-SNAPSHOT"
    }
    
    configurations.all {
        resolutionStrategy.cacheChangingModulesFor 0, 'seconds'
    }
}

apply plugin: 'hyperskill'
```

## Versions

The plugin contains the following versions structure:

```gradle
hs {
    android {
        robolectricVersion = "4.3.1"
        kotlinVersion = "1.4.20"
        compileSdkVersion = 29
        minSdkVersion = 20
        targetSdkVersion = 29
    }

    gradle {
        version = "7.1.1"
    }

    java {
        version = 11
    }

    kotlin {
        version = "1.5.20"
    }

    spring {
        bootVersion = "2.3.1.RELEASE"
        dependencyManagementVersion = "1.0.9.RELEASE"
    }
}
```

## Accessing and overriding version

To acces a version variable from the plugin you should use `hs` object:

```
hs.gradle.version
hs.java.version
hs.android.minSdkVersion
```

To override version you can assign needed version to the variables before using them:

```
hs.java.version = 17
```
