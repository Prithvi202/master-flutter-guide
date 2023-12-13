# Deployment and Distribution

Welcome to the Deployment and Distribution guide! In this section, we'll cover building and releasing Flutter apps, app store deployment for Google Play Store and Apple App Store, and Continuous Integration/Continuous Deployment (CI/CD) for Flutter.

## Building and Releasing Flutter Apps

Building and releasing a Flutter app involves running the following commands:

```bash
flutter build apk   # For Android
flutter build ios   # For iOS
```
To release, follow platform-specific steps for signing and packaging.

## App Store Deployment
### Google Play Store
Generate a keystore:
```bash
keytool -genkey -v -keystore key.keystore -keyalg RSA -keysize 2048 -validity 10000 -alias key
```
Build the release APK:
```bash
flutter build appbundle
```
Upload the generated bundle to the Google Play Console.

### Apple App Store
Set up Xcode project settings.

Archive your app in Xcode.

Upload the archive to App Store Connect.

## Continuous Integration/Continuous Deployment (CI/CD) for Flutter
Use CI/CD tools like Jenkins, Travis CI, or GitHub Actions to automate testing, building, and deploying your Flutter app.

Here's an example GitHub Actions workflow:
```yaml
name: CI/CD

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v2

      - name: Set up Flutter
        uses: subosito/flutter-action@v2
        with:
          flutter-version: '2.8.0'  # Set your Flutter version

      - name: Get dependencies
        run: flutter pub get

      - name: Run tests
        run: flutter test

      - name: Build release APK
        run: flutter build apk

      - name: Deploy to Google Play
        uses: wzieba/FakeGooglePlay@v1
        with:
          artifacts: build/app/outputs/flutter-apk/app-release.apk
          track: internal
          rollout: 1%
```
