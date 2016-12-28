gradle plugin for ctrip [DynamicAPK](https://github.com/CtripMobile/DynamicAPK).
---
###hot to use
### root project build.gradle
* MDynamicHome/build.gradle
```
    jcenter()
    dependencies {
        classpath 'com.mlibrary:dynamic:0.0.1'
    }
```
```
    apply plugin: 'com.android.application'
    apply plugin: 'com.mlibrary.dynamic.application'

    dynamicApplication {
        solidMode = project.solidMode
        buildToolsVersion = project.buildToolsVersion
        supportLibraryVersion = project.supportLibraryVersion
        packageName = "com.mctrip"
        moduleConfigFilePath = "$rootDir/gradle/dynamic/apk_module_config.xml"
        keystore = "$rootDir:MApps:MCtripApp/debug.keystore"
        keyAlias = "androiddebugkey"
        keyPassword = "android"
        storePassword = "android"
    }
```
```
    apply plugin: 'com.android.library'
    apply plugin: 'com.mlibrary.dynamic.library'

    dynamicLibrary {
        packageName = "com.mctrip.modules.device"
        moduleProguardRulesFilePath = "$rootDir/gradle/dynamic/sub-project-proguard-rules.pro"
    }
```
###exambles
https://github.com/mlibrarys/MDynamicHome
---