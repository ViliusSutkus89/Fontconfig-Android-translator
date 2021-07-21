# Fontconfig-Android-translator

[![Maven Central](https://img.shields.io/maven-central/v/com.viliussutkus89/fontconfig-android-translator.svg?label=Maven%20Central)](https://search.maven.org/search?q=g:com.viliussutkus89%20AND%20a:fontconfig-android-translator)

[Fontconfig](https://www.freedesktop.org/wiki/Software/fontconfig/) is a library for configuring and customizing font access.
To be usable by end applications, this library requires configuration.

Android provides some configuration, but it is not available for regular Linux programs and libraries that expect Fontconfig to just work.

This software is a translator which consumes Android's config XML files and produces an XML file that could be understood by Fontconfig.

Android systems from API level 21 provide config in /system/etc/fonts.xml, older versions provide it in /system/etc/system_fonts.xml

## How to install:
Library needs to be included as a dependency in the app level build.gradle:
```gradle
dependencies {
    implementation 'com.viliussutkus89:fontconfig-android-translator:1.0.0'
}
```

Fontconfig-Android-translator is distributed using [Maven Central](https://search.maven.org/artifact/com.viliussutkus89/fontconfig-android-translator) repository.  
It needs be added to top level build.gradle:
```gradle
allprojects {
  repositories {
      // ...
      mavenCentral()
  }
}
```

## Usage

Translator is interfaced through Java.
```Java
import com.viliussutkus89.android.fontconfigtranslator.FontconfigTranslator;
File result = new File(context.getCacheDir(), "fontconfig/system-etc-fonts-xml-translated.conf");
FontconfigTranslator.translate(result);
```
