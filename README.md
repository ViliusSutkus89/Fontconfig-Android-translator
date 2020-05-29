# Fontconfig-Android-translator

![Build](https://github.com/ViliusSutkus89/Fontconfig-Android-translator/workflows/Build/badge.svg)
[![Download](https://api.bintray.com/packages/viliussutkus89/maven-repo/Fontconfig-Android-translator/images/download.svg)](https://bintray.com/viliussutkus89/maven-repo/Fontconfig-Android-translator/_latestVersion)

[Fontconfig](https://www.freedesktop.org/wiki/Software/fontconfig/) is a library for configuring and customizing font access.
To be usable by end applications, this library requires configuration.

Android provides some configuration, but it is not available for regular Linux programs and libraries that expect Fontconfig to just work.

This software is a translator which consumes Android's config XML files and produces an XML file that could be understood by Fontconfig.

Android systems from API level 21 provide config in /system/etc/fonts.xml, older versions provide it in /system/etc/system_fonts.xml

## Usage

Translator is interfaced through Java.
```Java
import com.viliussutkus89.android.fontconfigtranslator.FontconfigTranslator;
File result = new File(context.getCacheDir(), "fontconfig/system-etc-fonts-xml-translated.conf");
FontconfigTranslator.translate(result);
```

Include the library in app level build.gradle.

```gradle
dependencies {
    implementation 'com.viliussutkus89:fontconfig-android-translator:0.9.9'
}
```

Fontconfig-Android-translator is distributed using [JCenter](https://jcenter.bintray.com) Maven repository.  
It needs be added to top level build.gradle.
```gradle
allprojects {
    repositories {
        jcenter()
    }
}
```

Older versions of Gradle (or Android Gradle plugin?) require JCenter url.
```gradle
allprojects {
    repositories {
        maven() {
            url  "https://jcenter.bintray.com"
        }
    }
}
```
