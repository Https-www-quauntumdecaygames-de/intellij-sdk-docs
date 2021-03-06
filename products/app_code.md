---
title: AppCode Plugin Development
---

## Introduction
Plugin projects targeting [AppCode](https://www.jetbrains.com/objc/) can be developed using IntelliJ IDEA with the `gradle-intellij-plugin`.

## Configuring Plugin Projects Targeting AppCode
The Gradle configuration of AppCode plugin projects uses neither Product-Specific nor IntelliJ IDEA Attributes.
Instead, configure AppCode plugin projects to use the `intellij.localPath` attribute.

> **Note** AppCode plugin development requires installing AppCode locally.

The table below summarizes the `gradle-intellij-plugin` attributes to set in the `build.gradle` file:

| `gradle-intellij-plugin` Attribute | Attribute Value |
|-----------|-------|
| [`intellij.localPath`](https://github.com/JetBrains/gradle-intellij-plugin/blob/master/README.md#intellij-platform-properties) | Path to locally installed target version of AppCode. For example, for macOS:<br>`/Users/<user name>/Library/Application Support/JetBrains/Toolbox/apps/AppCode/ch-0/193.5662.55/AppCode.app/Contents`  |
| [`runIde.ideaDirectory`](https://github.com/JetBrains/gradle-intellij-plugin/blob/master/README.md#running-dsl) | Path to locally installed target version of AppCode. For example, for macOS:<br>`/Users/<user name>/Library/Application Support/JetBrains/Toolbox/apps/AppCode/ch-0/193.5662.55/AppCode.app/Contents` |

The dependency on the AppCode APIs must be declared in the `plugin.xml` file.
As described in [Modules Specific to Functionality](/basics/getting_started/plugin_compatibility.md#modules-specific-to-functionality) table, the `<depends>` tags must declare `com.intellij.modules.appcode`.

## Available AppCode APIs
Use the [Exploring APIs as a Consumer](/basics/getting_started/plugin_compatibility.md#exploring-apis-as-a-consumer) process to identify the libraries in AppCode.
Test your plugin with any version of AppCode you wish to support.
