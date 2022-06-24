# Using Compose Compiler to support different versions of Kotlin

For the purposes of testing, development, or just living on the edge... some people want to use
versions of Kotlin that are not yet officially supported by the Compose Compiler.  For this purpose,
we publish some branches the Compose Compiler that follow various versions of the Kotlin Compiler.

It is worth noting that these builds of the Compose Compiler typically undergo less testing than
the final builds published on Gmaven, so adopt at your own risk.

# Compatibility table

To see a table of Kotlin versions and their matching Compose Compiler versions, check out the compatibility table on androidx.dev:
[https://androidx.dev/storage/compose-compiler/repository](https://androidx.dev/storage/compose-compiler/repository)

# Project Configuration

This repository contains an example Compose project using pre-release builds of both the Kotlin and
the Compose Compiler, while pointing to stable versions of the Compose UI libraries.

Specifically, there are two things to point out:

 - [settings.gradle:14](https://github.com/jimgoog/ComposeAppUsingPrereleaseComposeCompiler/blob/main/settings.gradle#L14) adds the maven repository:
   
   ```
      maven {
        url "https://androidx.dev/storage/compose-compiler/repository/"
      }
   ```
 - [app/build.gradle:39](https://github.com/jimgoog/ComposeAppUsingPrereleaseComposeCompiler/blob/main/app/build.gradle#L39) specifies the compose compiler version:

    ```
      composeOptions {
        kotlinCompilerExtensionVersion "1.2.0-dev-k1.6.20-RC2-727605f905e"
      }
   ```
