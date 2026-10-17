# Laporkita

Flutter prototype for community reports, chat, status tracking, and map-based
report location selection.

## Google Maps setup

The map screen uses `google_maps_flutter`. Create a Google Maps API key in
Google Cloud, enable billing, and enable the Maps SDK that matches each target.
Restrict each key to the app/domain where it is used. Do not commit an
unrestricted production key.

Replace `YOUR_GOOGLE_MAPS_API_KEY` in the following locations with the key for
the corresponding platform:

- **Web:** `web/index.html` — enable **Maps JavaScript API** and add the local
  development and production domains to the HTTP referrer restrictions.
- **Android:** `android/app/src/main/AndroidManifest.xml` — enable **Maps SDK
  for Android** and restrict the key by this app's Android application ID and
  signing certificate SHA-1.

- **iOS:** `ios/Runner/AppDelegate.swift` — enable **Maps SDK for iOS** and
  restrict the key by the app's bundle ID.

The initial camera and selected map pin use a sample point in Jakarta. Users
can tap anywhere on the map to choose another report location. Update
`MapLocationModel.initialPosition` in `lib/model/map_location_model.dart` to
set the initial point to your service area.

## Run

```sh
flutter pub get
flutter run
```
