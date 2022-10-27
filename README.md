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
2.Add Internet permission in your manifest
```kotlin
   <uses-permission android:name="android.permission.INTERNET" />
```
## GoogleMap
1. Create a composable function called MainMaps, in this fuction we will add GoogleMap like this
```kotlin
val singapore = LatLng(1.35, 103.87)
val cameraPositionState = rememberCameraPositionState {
    position = CameraPosition.fromLatLngZoom(singapore, 10f)
}
GoogleMap(
    modifier = Modifier.fillMaxSize(),
    cameraPositionState = cameraPositionState
)
```
2.Run your App on an android Emulator,
the result must be like this <br>
<img src="" width="" height=""/>
## Add Marker 
