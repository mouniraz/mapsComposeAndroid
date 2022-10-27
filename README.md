# mapsComposeAndroid
how to create a google maps activity with compose on android
## Add dependency
1. create an Android project with empty compose Activity using android Studio
2. Add dependencies in builde.gradle and synchronise Projects
```kotlin
  implementation 'com.google.maps.android:maps-compose:2.5.3'
  implementation 'com.google.android.gms:play-services-maps:18.0.2'
```
## API key
1. go to < a href="https://console.cloud.google.com/projectselector2/google/maps-apis/credentials?_ga=2.260275981.1655667289.1666777268-1034129582.1662745390"> API key </a>
2. get api key (must start with Aiza...)
3. put the api key in the manifest in the application tag
```kotlin
        <meta-data
            android:name="com.google.android.geo.API_KEY"
            android:value="AIza......" />

```

