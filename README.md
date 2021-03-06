# RSSTS
RSSTS = Report Screenshot To Slack

You can report a screenshot of your application to slack channels that you like.

### When one activity starts, RSSTS's notification will be shown.
![](https://github.com/gotokatsuya/RSSTS/blob/master/notification1.png)

### When you tap this notification, Screenshot will be sent to a slack channel.
![](https://github.com/gotokatsuya/RSSTS/blob/master/notification2.png)

![](https://img.shields.io/badge/Android%20Arsenal-RSSTS-brightgreen.svg?style=flat)
## How to use
```java
public class YourApplication extends Application {

    @Override
    public void onCreate() {
        super.onCreate();

        // Initialize Rssts
        Rssts.initialize(true, "your slack token", "your slack channel ID");

        // Start Rsstser of Your Application
        Rsstser.start(this);
    }

    // Maybe, this method is called when you use emulator
    @Override
    public void onTerminate() {

        // Stop Rsstser of Your Application
        Rsstser.stop(this);
        super.onTerminate();
    }
}
```

You should look [this sample code](https://github.com/gotokatsuya/RSSTS/tree/master/app/src/main/java/com/goka/sample/application).

Application.ActivityLifecycleCallbacks is used by sample code but it is released from API-14.
When the api that you use is lower than 14, you have to use compat-ActivityLifecycleCallbacks.
Check [this sample](https://github.com/gotokatsuya/RSSTS/tree/master/app/src/main/java/com/goka/sample/application/suport).

## Gradle
```java
repositories {
    jcenter()
}

dependencies {
    compile 'com.github.goka.rssts:library:1.0.0'
}
```

## iOS

Check [this repository](https://github.com/kaneshin/RSSTS) !


## OSX

Check [this repository](https://github.com/kaneshin/RSSTSOSX) !
