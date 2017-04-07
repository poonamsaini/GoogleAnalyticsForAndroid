# GoogleAnalyticsForAndroid
Google analytics to show how to add Analytics to your Android app to measure user activity for personal or corporation purpose.

# Prerequisites
Latest versions of Android Studio and Google Play Services

# Getting Started
1. Start a new Project in Android studio with blank Activity.
2. Add following permission in MANIFEST FILE
 ```
  <uses-permission android:name="android.permission.INTERNET"/>
  <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
   ```
3. Gradle 
  1. Add the following dependency under project level gradle
   ```
    classpath 'com.google.gms:google-services:3.0.0'
    ```
  2. Add the following dependency under app level gradle
    ```
    classpath 'com.google.gms:google-services:3.0.0'
    ```
  3. Add the following plugin under app level gradle
  ```
    apply plugin: 'com.google.gms.google-services'
    ```

  
