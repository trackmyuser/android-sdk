# Android SDK

## Integrating the the SDK

### Download the SDK from the release section

https://github.com/user-attachments/assets/e31eacaa-2d18-4372-a0dc-3b7c99fec332

### Create a folder called 'libs' in your app's root directory and paste the SDK

https://github.com/user-attachments/assets/2cc90c18-ea9a-4d14-bf85-bf6906bd5e27

### Add the SDK as a dependency in your gradle file

https://github.com/user-attachments/assets/1ba08d26-36e9-45b9-b3d7-32f54588e223

## Initialising the SDK

### Copy the SDK key from the dashboard

https://github.com/user-attachments/assets/358e0681-4dcc-4a09-8754-452fa6b744a3

### Call the init method as soon as your app boots up

#### Java

```java
import com.trackmyuser.sdk.TrackMyUser;

public class BootActivity extends AppCompatActivity {

    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        
        String userId = "-4f3fa9c2844335b316b41ff1";
        String sdkKey = "16b41ff1-c40a-4f3f-9eff-a9c2844335b3";
        
        TrackMyUser.init(this, sdkKey);
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
        TrackMyUser.setUserId(userId)
    }
}
```

## Event Tracking

### Create an event in the dasboard

https://github.com/user-attachments/assets/9b4c796b-77ee-4626-bb7c-0fafdb70aa69

### Call the trackEvent method

#### Java

```java
import com.trackmyuser.sdk.TrackMyUser;
import com.trackmyuser.sdk.TrackMyUserEvent;

public class HomeActivity extends AppCompatActivity {

    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        
        Double adRevenue = 10.0;
        TrackMyUserEvent adImpressionEvent = new TrackMyUserEvent("AD_IMPRESSION");
        event.setRevenue("INR", adRevenue);
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

        val adRevenue = 10.0
        val adImpressionEvent = TrackMyUserEvent("AD_IMPRESSION")
        adImpressionEvent.setRevenue("INR", adRevenue)
        TrackMyUser.trackEvent(this, adImpressionEvent)
    }
}
```
