# Firebase Setup Guide for Flutter App

This guide will help you set up Firebase authentication in your Flutter app.

## Prerequisites

1. A Google account
2. Flutter SDK installed
3. Android Studio / VS Code with Flutter extensions

## Step 1: Create a Firebase Project

1. Go to [Firebase Console](https://console.firebase.google.com/)
2. Click "Create a project" or "Add project"
3. Enter a project name (e.g., "flutter-app02")
4. Choose whether to enable Google Analytics (recommended)
5. Click "Create project"

## Step 2: Enable Authentication

1. In your Firebase project, click on "Authentication" in the left sidebar
2. Click "Get started"
3. Go to the "Sign-in method" tab
4. Enable "Email/Password" authentication
5. Click "Save"

## Step 3: Add Android App

1. In your Firebase project, click on the gear icon (⚙️) next to "Project Overview"
2. Select "Project settings"
3. Scroll down to "Your apps" section
4. Click the Android icon (🤖)
5. Enter your Android package name: `com.example.flutter_app02`
6. Enter app nickname (optional)
7. Click "Register app"
8. Download the `google-services.json` file
9. Place it in `android/app/` directory

## Step 4: Add Web App (Optional)

1. In the same "Your apps" section, click the web icon (</>)
2. Enter app nickname (optional)
3. Click "Register app"
4. Copy the Firebase configuration object
5. Replace the placeholder values in `web/index.html` with your actual Firebase config

## Step 5: Install Dependencies

Run the following command in your project root:

```bash
flutter pub get
```

## Step 6: Update Firebase Config

### For Android:
- The `google-services.json` file should already be in place
- The build.gradle files have been updated automatically

### For Web:
- Update the Firebase configuration in `web/index.html` with your actual values from Firebase console

## Step 7: Test the App

1. Run the app: `flutter run`
2. The app will show a login screen
3. Create a new account or sign in with existing credentials
4. After successful authentication, you'll be redirected to the home screen

## Features

- **Email/Password Authentication**: Users can sign up and sign in
- **Form Validation**: Email format and password length validation
- **Error Handling**: Proper error messages for various authentication scenarios
- **Auto-navigation**: Automatic redirection based on authentication state
- **Logout Functionality**: Users can sign out from the home screen

## Troubleshooting

### Common Issues:

1. **"Target of URI doesn't exist"**: Run `flutter pub get` to install dependencies
2. **Firebase initialization error**: Check if `google-services.json` is in the correct location
3. **Authentication not working**: Verify that Email/Password authentication is enabled in Firebase console

### Getting Firebase Config Values:

- **apiKey**: Found in Project Settings > General > Your apps
- **authDomain**: Usually `your-project-id.firebaseapp.com`
- **projectId**: Your Firebase project ID
- **storageBucket**: Usually `your-project-id.appspot.com`
- **messagingSenderId**: Found in Project Settings > General > Your apps
- **appId**: Found in Project Settings > General > Your apps

## Security Notes

- Never commit your actual Firebase configuration to version control
- Use environment variables or secure configuration management for production
- Enable appropriate security rules in Firebase console
- Consider implementing additional authentication methods (Google, Facebook, etc.) for production apps

## Next Steps

After basic authentication is working, you can:

1. Add password reset functionality
2. Implement email verification
3. Add social authentication (Google, Facebook, etc.)
4. Create user profiles and data storage
5. Implement role-based access control
6. Add biometric authentication

## Support

If you encounter issues:
1. Check the [Firebase Flutter documentation](https://firebase.flutter.dev/)
2. Review [Flutter documentation](https://docs.flutter.dev/)
3. Check Firebase console for error logs
4. Verify all configuration files are in the correct locations
