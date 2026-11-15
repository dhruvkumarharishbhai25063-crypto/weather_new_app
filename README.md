# 🌦️ Weather App

A cross-platform weather application built with **Flutter** and **Dart**. It retrieves real-time weather data from a REST API and presents current conditions in a clean, responsive Material UI.

---

## ✨ Features

- 🌍 Current weather for any city worldwide
- 🌡️ Temperature, "feels like", humidity, pressure and wind speed
- ☁️ Weather condition with matching icon
- 🕒 Localised date and time formatting
- ⚡ Asynchronous API calls with loading and error states
- 📱 Responsive Material Design layout

---

## 🧰 Tech Stack

| Layer | Technology |
|-------|------------|
| Framework | Flutter |
| Language | Dart (SDK `^3.11.1`) |
| Networking | [`http`](https://pub.dev/packages/http) `^0.13.6` |
| Date/Time | [`intl`](https://pub.dev/packages/intl) `^0.18.0` |
| Icons | Material Icons, `cupertino_icons` |
| Linting | `flutter_lints` |

---

## 🏗️ How It Works

```
User enters city
      │
      ▼
 HTTP GET request  ──►  Weather API
      │                     │
      ▼                     ▼
 Parse JSON response  ◄──  JSON data
      │
      ▼
 Update UI (temperature, condition, humidity, wind)
```

1. The user searches for a city.
2. The app sends an HTTP request using the `http` package.
3. The JSON response is decoded into Dart objects.
4. The UI rebuilds to show the latest weather data.
5. Errors (no internet, invalid city, API failure) are caught and shown to the user.

---

## 📁 Project Structure

```
weather_new_app/
├── lib/
│   └── main.dart          # App entry point and UI
├── android/               # Android platform files
├── ios/                   # iOS platform files
├── test/                  # Widget and unit tests
├── pubspec.yaml           # Dependencies and metadata
├── analysis_options.yaml  # Lint rules
└── README.md
```

> Adjust this tree if you split the code into `models/`, `services/`, `screens/` and `widgets/`.

---

## 🚀 Getting Started

### Prerequisites

- [Flutter SDK](https://docs.flutter.dev/get-started/install) installed and on your PATH
- Dart SDK `3.11.1` or higher (bundled with Flutter)
- Android Studio or VS Code with the Flutter plugin
- An emulator or a physical device with USB debugging enabled

Verify your setup:

```bash
flutter doctor
```

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/weather_new_app.git

# 2. Move into the project
cd weather_new_app

# 3. Install dependencies
flutter pub get

# 4. Run the app
flutter run
```

### 🔑 API Key Setup

This app needs an API key from a weather provider such as [OpenWeatherMap](https://openweathermap.org/api).

1. Create a free account and generate a key.
2. Add the key to your code:

   ```dart
   const String apiKey = 'YOUR_API_KEY_HERE';
   ```

> ⚠️ Do not commit your real key. Keep it out of version control, for example by loading it with `--dart-define`:
>
> ```bash
> flutter run --dart-define=WEATHER_API_KEY=your_key
> ```
> ```dart
> const apiKey = String.fromEnvironment('WEATHER_API_KEY');
> ```

---

## 📦 Build

```bash
# Android APK
flutter build apk --release

# Android App Bundle
flutter build appbundle --release

# Web
flutter build web
```

The APK is generated at `build/app/outputs/flutter-apk/app-release.apk`.

---

## 🧪 Testing and Code Quality

```bash
flutter analyze   # static analysis
flutter test      # run tests
```

---

## 🛠️ Troubleshooting

| Problem | Fix |
|---------|-----|
| `flutter pub get` fails | Make sure `cupertino_icons` is indented under `dependencies:` in `pubspec.yaml` |
| 401 Unauthorized from API | Check that your API key is valid and activated |
| City not found | Check the spelling or try `City,CountryCode` |
| No data on Android | Confirm `INTERNET` permission in `AndroidManifest.xml` |

Required Android permission (`android/app/src/main/AndroidManifest.xml`):

```xml
<uses-permission android:name="android.permission.INTERNET"/>
```

---

## 🗺️ Roadmap

- [ ] 5-day and hourly forecast
- [ ] GPS-based current location weather
- [ ] Unit toggle (°C / °F)
- [ ] Dark mode
- [ ] Favourite cities
- [ ] Offline caching

---

## 🤝 Contributing

1. Fork the repository
2. Create a branch: `git checkout -b feature/your-feature`
3. Commit your changes: `git commit -m "Add your feature"`
4. Push the branch: `git push origin feature/your-feature`
5. Open a pull request

---

## 📄 License

Distributed under the MIT License.
