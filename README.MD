![logo](https://github.com/user-attachments/assets/0d41b803-968a-41a8-809a-0dd3d91ec489)

## Integrating the the SDK

### 1. Add the SDK as a dependency in your gradle file

https://github.com/user-attachments/assets/1ba08d26-36e9-45b9-b3d7-32f54588e223

#### Add these permissions in your AndroidManifest.xml

```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
<uses-permission android:name="com.google.android.gms.permission.AD_ID"/>
```
#### Add these dependencies to your build.gradle

```gradle
dependencies {
    implementation 'com.github.trackmyuser:android-sdk:0.2.18'
}
```

## Initialising the SDK

### 1. Copy the SDK key from the dashboard

https://github.com/user-attachments/assets/358e0681-4dcc-4a09-8754-452fa6b744a3

### 2. Call the init method as soon as your app boots up

#### Java

```java
import com.trackmyuser.sdk.TrackMyUser;

public class BootActivity extends AppCompatActivity {

    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        
        String userId = "-4f3fa9c2844335b316b41ff1";
        String sdkKey = "16b41ff1-c40a-4f3f-9eff-a9c2844335b3";
        
        TrackMyUser.init(this, sdkKey);
        //optional
        TrackMyUser.setUserId(userId);
    }
}
```

#### Kotlin

```kotlin
import com.trackmyuser.sdk.TrackMyUser

class BootActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        val userId = "-4f3fa9c2844335b316b41ff1"
        val sdkKey = "16b41ff1-c40a-4f3f-9eff-a9c2844335b3"

        TrackMyUser.init(this, sdkKey)
        //optional
        TrackMyUser.setUserId(userId)
    }
}
```

## Event Tracking

### 1. Create an event in the dasboard

https://github.com/user-attachments/assets/9b4c796b-77ee-4626-bb7c-0fafdb70aa69

### 2. Call the trackEvent method

#### Java

```java
import com.trackmyuser.sdk.TrackMyUser;
import com.trackmyuser.sdk.TrackMyUserEvent;

public class HomeActivity extends AppCompatActivity {

    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        
        TrackMyUserEvent adImpressionEvent = new TrackMyUserEvent("AD_IMPRESSION");
        //optional
        Double adRevenue = 10.0;
        adImpressionEvent.setRevenue("INR", adRevenue);
        //
        TrackMyUser.trackEvent(this, adImpressionEvent);
    }
}
```

#### Kotlin

```kotlin
import com.trackmyuser.sdk.TrackMyUser
import com.trackmyuser.sdk.TrackMyUserEvent

class HomeActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        val adImpressionEvent = TrackMyUserEvent("AD_IMPRESSION")
        //optional
        val adRevenue = 10.0
        adImpressionEvent.setRevenue("INR", adRevenue)
        //
        TrackMyUser.trackEvent(this, adImpressionEvent)
    }
}
```
