## Getting Started

Build aar for native usage

```
fvm flutter build aar
```

Follow config maven and dependencies

```
Consuming the Module
  1. Open <host>/app/build.gradle
  2. Ensure you have the repositories configured, otherwise add them:

      String storageUrl = System.env.FLUTTER_STORAGE_BASE_URL ?: "https://storage.googleapis.com"
      repositories {
        maven {
            url '/Users/manzer/development/devFlutter/spike/spike_widget_to_native/build/host/outputs/repo'
        }
        maven {
            url "$storageUrl/download.flutter.io"
        }
      }

  3. Make the host app depend on the Flutter module:

    dependencies {
      debugImplementation 'com.example.spike_widget_to_native:flutter_debug:1.0'
      profileImplementation 'com.example.spike_widget_to_native:flutter_profile:1.0'
      releaseImplementation 'com.example.spike_widget_to_native:flutter_release:1.0'
    }


  4. Add the `profile` build type:

    android {
      buildTypes {
        profile {
          initWith debug
        }
      }
    }

```