AndroidWearCrashReport
======================
Allows you to retrieve exceptions of an Android Wear app in your handheld's one. It is particularly useful if you're using a Crash Reporting library or if you implemented a way to retrieve crashes.


## Download

### In your wear app
```
dependencies {
    compile 'fr.nicolaspomepuy.androidwearcrashreport:crashreport-wear:0.4@aar'
}
```

### In your mobile app
```
dependencies {
    compile 'fr.nicolaspomepuy.androidwearcrashreport:crashreport-mobile:0.4@aar'
}
```

## Usage

To work, these lines should be added int the onCreate method of your ```Application``` or main ```Activity``` class

### In your mobile app
```java
CrashReport.getInstance(this).setOnCrashListener(new CrashReport.IOnCrashListener() {
    @Override
    public void onCrashReceived(CrashInfo crashInfo) {
        // Manage the crash
    }
});
```

You can also send the Report to the Play Store by calling this method:

```java
CrashReport.getInstance(this).reportToPlayStore(this);
```

### In your wear app
```java
CrashReporter.getInstance(this).start();
```

You can also send caught exceptions

```java
CrashReporter.getInstance(this).sendException(yourException);
```
## Thanks

Special thanks to Aladin Q. for his help on the Play Store report

## License

```
 Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
```
