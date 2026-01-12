# Overview

This is a mobile application designed to provide support resources for domestic violence survivors. The app includes emergency contact management, safety planning tools, educational resources, and 24/7 helpline access. All data is stored locally on the user's device for privacy and security.

**Purpose:** Create a safe, accessible mobile tool that helps domestic violence survivors access support resources and plan for their safety.

**Key Features:**

- 5 interactive screens with full navigation
- Emergency contacts management (add, delete, call, text)
- Personal safety plan creator with persistent storage
- Educational resources about domestic violence
- Quick-dial access to national hotlines
- Phone integration for calling and texting
- AsyncStorage for data persistence
- Quick exit button for user safety

[Software Demo Video](YOUR_VIDEO_LINK_HERE)

# Development Environment

**Tools Used:**

- Visual Studio Code (code editor)
- Node.js v20+ (JavaScript runtime)
- Expo Go app (for testing on iPhone)
- Git & GitHub (version control)

**Programming Language & Libraries:**

- JavaScript (React Native)
- React Navigation 7.x (screen navigation)
- AsyncStorage 2.2.0 (local data storage)
- Expo SDK 54 (mobile framework)
- React 19.1.0

**Setup Instructions:**

1. Install Node.js from nodejs.org
2. Clone this repository
3. Run `npm install --legacy-peer-deps`
4. Run `npm start`
5. Scan QR code with Expo Go app on your phone

# Useful Websites

- [React Native Documentation](https://reactnative.dev/docs/getting-started) - Official React Native docs
- [Expo Documentation](https://docs.expo.dev/) - Expo framework guides and API reference
- [React Navigation Docs](https://reactnavigation.org/docs/getting-started) - Navigation library documentation
- [AsyncStorage Guide](https://react-native-async-storage.github.io/async-storage/) - Local storage documentation
- [National DV Hotline](https://www.thehotline.org/) - Resource information for app content

# Future Work

- Add ability to edit existing emergency contacts (currently can only add/delete)
- Implement a password/PIN lock feature for app security
- Add ability to upload and store photos of important documents
- Create a "disguise mode" that makes the app look like a different app (weather, calculator, etc.)
- Add multi-language support (Spanish, etc.)
- Include a safety timer that sends alerts if not checked in
- Add local shelter finder using location services
- Implement encrypted backup of safety plan to cloud storage
