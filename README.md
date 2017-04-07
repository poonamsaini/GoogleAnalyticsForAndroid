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
  
  - Go to [Google Developer Page](https://developers.google.com/mobile/add?platform=android&cntapi=analytics&cnturl=https:%2F%2Fdevelopers.google.com%2Fanalytics%2Fdevguides%2Fcollection%2Fandroid%2Fv4%2Fapp%3Fconfigured%3Dtrue&cntlbl=Continue%20Adding%20Analytics).
  - Sign in using your google account.
  - Give your app name and package name.
  - Select your country and hit choose and configure services.
  - Choose create a new Analytics property if it is a new project or else choose your project from drop down.
  - Provide your country name and timezone and click enable analytical service. 
  - Your analytics tracking ID will be generated. Click on generate configuration files to generate the json file.
  - Download your google-services.json and then paste it inside the app folder of your project (project/app).
  
# CODE 
1. Create a class extending application to return your application's tracker for eg- AnalyticApplication extends Application.
  ```js
   private Tracker applicationTracker;

    synchronized public Tracker getDefaultTracker() {
        if (applicationTracker == null) {
            GoogleAnalytics googleAnalytics = GoogleAnalytics.getInstance(this);
            applicationTracker = googleAnalytics.newTracker(R.xml.global_tracker);
        }
        return applicationTracker;
    }
   ```
   Register the name of the application in manifest.
   ```js
   <application
        android:name=".AnalyticApplication"
        ....
   ```
 2. In onCreate of your mainActivity get a refrence of your application tracker.
  ```js
    AnalyticApplication application = (AnalyticApplication) getApplication();
        applicationTracker = application.getDefaultTracker();
  ```
 3. Register all your tracking events in this case screens (be it a activity or a fragment) via [call onresume function to keep track of how many times it has been used by the customer]
   ```js
   applicationTracker.setScreenName("mainActivity");
        applicationTracker.send(new HitBuilders.ScreenViewBuilder().build());
   ```
 4. Forward the data to server [depends on the developer that how often and with what interval they want to send it] via
   ```js
  applicationTracker.send(new HitBuilders.EventBuilder()
                .setCategory("Action")
                .setAction("Share")
                .build());
   ```
   
## Monitor the application analytics
1. Build your app and run it on emulator or yoyr device.
2. Go to [analytics.google.com](https://analytics.google.com/analytics/web/)
3. Login using your google account.
4. Click on  real time on left slider. YOu can monitor your analytics here.

**NOTE-** It might take upto a minute to load the data.
   
   https://ga-dev-tools.appspot.com/hit-builder/
  

  
  

  
