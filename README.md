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
GoogleMap(
    modifier = Modifier.fillMaxSize(),
    cameraPositionState = cameraPositionState
)
```
2.Run your App on an android Emulator,

## Add Marker 
1. Add a Marker in Singapore and change position camera to this point
```kotlin
 val singapore = LatLng(1.35, 103.87)
                    val cameraPositionState = rememberCameraPositionState {
                        position = CameraPosition.fromLatLngZoom(singapore, 10f)
                    }
                    GoogleMap(
                        modifier = Modifier.fillMaxSize(),
                        cameraPositionState = cameraPositionState,
                        

                    ) {
                        Marker(
                            state = MarkerState(position = singapore),
                            title = "Singapore",
                            snippet = "Marker in Singapore"
                        )
                    }          
```
2. change position marker to Tunisia and run your app
3. change the zoom degree from 10f to 5f then to 15f, see what happen

## Type of Map
1. change type of Map to satellite using properties of Map

```kotlin
var properties by remember {
                    mutableStateOf(MapProperties(mapType = MapType.SATELLITE))
                }
                
                
                .....
                GoogleMap(
                        modifier = Modifier.fillMaxSize(),
                        cameraPositionState = cameraPositionState,
                        properties=properties

                    )
```
3. test the other type of map: none,normal,hybrid
## Points of Interests:Poi
1. on click on Poi display message that contain the name of Poi in a snackbar

```kotlin
  onPOIClick = {


                       Log.d("Tag","POI clicked: ${it.name}")


                }
```

