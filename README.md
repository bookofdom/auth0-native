## 1. Install

Install the dependencies with [Yarn](https://yarnpkg.com):

```bash
yarn install
```

### iOS Applications only

Change the directory into the `ios` folder and run the following command to install the SDK pod with [CocoaPods](https://cocoapods.org/):

```bash
cd ios
pod install
```

You should see the `A0Auth0` pod being installed and linked to the sample app.

### Android applications only

Open the `android/app/build.gradle` file and locate the following manifest placeholders:

```groovy
android {
    defaultConfig {
        manifestPlaceholders = [auth0Domain: "YOUR_AUTH0_DOMAIN",
                                auth0Scheme: "${applicationId}"]
    }
    ...
}
```

Replace `YOUR_AUTH0_DOMAIN` with your Auth0 domain value. If you have `samples.auth0.com` as your Auth0 domain you would have a configuration like the following:

```groovy
android {
    defaultConfig {
        manifestPlaceholders = [auth0Domain: "samples.auth0.com", 
                                auth0Scheme: "${applicationId}"]
    }
    ...
}
```

The `applicationId` value will be auto-replaced at runtime with the package name or ID of your application (e.g. `com.example.app`).

## 2. Run The App

Run your app on an emulator, simulator, or your own connected device.

- To run the app on iOS run `yarn run ios`.
- To run the app on Android run `yarn run android`.

The first run may take a while to fully launch. Keep an eye out for confirmation windows and watch the terminal for output and results.

**Note:** If you get an error about "No bundle URL present" try clicking reload in the app or running `yarn run ios` again. 
