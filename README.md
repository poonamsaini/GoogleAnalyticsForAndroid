# GoogleAnalyticsForAndroid
Google analytics to show how to add Analytics to your Android app to measure user activity for personal or corporation purpose.

# Prerequisites
Latest versions of Android Studio and Google Play Services

# Getting Started
1. **Start a new Project in Android studio with blank Activity.**
2. **Add following permission in MANIFEST FILE**
 ```
  <uses-permission android:name="android.permission.INTERNET"/>
  <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
   ```
3. **Gradle** 
  - Add the following dependency under project level gradle
    ```
    classpath 'com.google.gms:google-services:3.0.0'
     ```
    
  - Add the following dependency under app level gradle
    ```
    compile 'com.google.android.gms:play-services-analytics:10.0.1'    
     ```
    
  - Add the following plugin under app level gradle
    ```
    apply plugin: 'com.google.gms.google-services'
     ```
4. **Getting json file**
  ```
  - Go to [Google Developer Page](https://developers.google.com/mobile/add?      platform=android&cntapi=analytics&cnturl=https:%2F%2Fdevelopers.google.com%2Fanalytics%2Fdevguides%2Fcollection%2Fandroid%2Fv4%2Fapp%3Fconfigured%3Dtrue&cntlbl=Continue%20Adding%20Analytics).
  - Sign in using your google account.
  - Give your app name and package name.
  - Select your country and hit choose and configure services.
  - Choose create a new Analytics property if it is a new project or else choose your project from drop down.
  - Provide your country name and timezone and click enable analytical service. 
  - Your analytics tracking ID will be generated. Click on generate configuration files to generate the json file.
  - Download your google-services.json and then paste it inside the app folder of your project (project/app).
   ```
  
  

  
