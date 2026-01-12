# Module 2 Video Script - DV Support App

**Target Time: 3-5 minutes**

---

## PART 1: INTRODUCTION (15 seconds)

**[Make sure your face is visible in a corner of the screen]**

**Say:**

> "Hi, I'm Kendahl Bingham. This is my Module 2 project - a Domestic Violence Support App. Let me show you how it works."

---

## PART 2: DEMO (1-2 minutes)

**[Screen record your phone with the app running]**

### A. Home Screen

**Show:** The home screen with all menu buttons

**Say:**

> "The app has five screens. The home screen shows all the main features."

### B. Emergency Contacts

**Show:**

1. Click "Emergency Contacts"
2. Click "Add Contact"
3. Fill in name and phone number
4. Click "Save Contact"
5. Click the "Contact" button on a saved contact
6. Show the call/text options

**Say:**

> "Users can add emergency contacts with names and phone numbers. When they tap a contact, they can call or text them directly using their phone."

### C. Safety Plan

**Show:**

1. Go back and click "Safety Plan"
2. Type something in one of the text boxes
3. Click "Save Safety Plan"
4. Go back to home, then back to Safety Plan to show it's still there

**Say:**

> "The safety plan lets users write down safe places to go, important documents, and emergency bag items. The data saves automatically so it's there even if they close the app."

### D. Helpline

**Show:**

1. Click "24/7 Helpline"
2. Show the national hotline numbers

**Say:**

> "The helpline screen has quick-dial buttons for the National Domestic Violence Hotline and emergency services."

### E. Resources

**Show:**

1. Click "Resources & Info"
2. Scroll through the information

**Say:**

> "The resources screen provides educational information about domestic violence and support organizations."

---

## PART 3: CODE WALKTHROUGH (2-3 minutes)

**[Screen share VS Code with your code open]**

### A. App Structure

**📁 Open File:** `App.js` (root folder)
**📍 Go to Lines:** 13-30

**Say:**

> "The app is built with React Native and uses React Navigation. In App.js, I set up five screens using Stack Navigator."

**Point to Lines 26-42** (the Stack.Screen components):

```javascript
<Stack.Screen name="Home" component={HomeScreen} />
<Stack.Screen name="EmergencyContacts" component={EmergencyContactsScreen} />
```

**Say:**

> "Each screen is a separate component that handles its own features."

---

### B. Phone Integration

**📁 Open File:** `src/screens/EmergencyContactsScreen.js`
**📍 Go to Lines:** 120-135 (scroll down to find the `handleCallContact` function)

**Say:**

> "For phone integration, I used React Native's Linking API. This function opens the phone's dialer when users tap a contact."

**Point to Line 130** (the Linking.openURL line):

```javascript
Linking.openURL(`tel:${contact.phone}`);
```

**Say:**

> "This line opens the phone dialer with the contact's number. I also have SMS integration with the sms: prefix."

---

### C. Local Storage

**📁 Open File:** `src/utils/storage.js`
**📍 Go to Lines:** 31-39 (the saveContacts function)

**Say:**

> "For data persistence, I created storage functions using AsyncStorage. This saves contacts and safety plans locally on the device."

**Point to Lines 31-39:**

```javascript
export const saveContacts = async (contacts) => {
  const jsonValue = JSON.stringify(contacts);
  await AsyncStorage.setItem(CONTACTS_KEY, jsonValue);
};
```

**Say:**

> "The saveContacts function converts the contacts array to JSON and stores it. Even if the user closes the app or turns off their phone, the data stays saved."

**📍 Scroll to Lines:** 50-56 (the getContacts function)

**Point to Lines 50-56:**

```javascript
export const getContacts = async () => {
  const jsonValue = await AsyncStorage.getItem(CONTACTS_KEY);
  return jsonValue != null ? JSON.parse(jsonValue) : [];
};
```

**Say:**

> "The getContacts function retrieves the saved data and converts it back from JSON."

---

### D. State Management

**📁 Open File:** `src/screens/EmergencyContactsScreen.js`
**📍 Go to Lines:** 36-44 (scroll to top of the component)

**Say:**

> "I used React hooks to manage the app's state. useState stores the contacts list, and useEffect loads the saved contacts when the screen opens."

**Point to Lines 36 and 43-45:**

```javascript
const [contacts, setContacts] = useState([]);

useEffect(() => {
  loadContacts();
}, []);
```

**Say:**

> "When users add or delete contacts, the state updates and the data saves to AsyncStorage immediately."

---

### E. Multiple Screens

**📁 Quickly open these files to show:**

- `src/screens/HomeScreen.js` (lines 1-10 to show the component)
- `src/screens/SafetyPlanScreen.js` (lines 1-10)
- `src/screens/HelplineScreen.js` (lines 1-10)

**Say:**

> "Each screen is a separate component with its own functionality. HomeScreen handles navigation, EmergencyContactsScreen manages the contacts list, and SafetyPlanScreen handles the safety planning forms."

---

## PART 4: CONCLUSION (15 seconds)

**Say:**

> "This app meets all the requirements: it has multiple screens, integrates with the phone for calling, stores data locally with AsyncStorage, and is fully interactive. The code has over 100 lines with detailed comments throughout. Thanks for watching!"

---

## QUICK CHECKLIST BEFORE RECORDING:

- [ ] Phone is charged and app is working
- [ ] VS Code is open with your code
- [ ] Camera/webcam is positioned to show your face
- [ ] Screen recording software is ready
- [ ] Audio is clear (test microphone)
- [ ] Remove any personal/sensitive info from screen
- [ ] Practice once before recording

## RECORDING TIPS:

1. Speak slowly and clearly
2. Pause briefly between sections
3. If you mess up, just pause, then continue from that sentence
4. Keep it simple - you don't need to explain every line of code
5. Smile and be confident - you built something great!

## AFTER RECORDING:

1. Upload to YouTube (unlisted is fine)
2. Copy the YouTube link
3. Update README.md with your video link (replace YOUR_VIDEO_LINK_HERE)
4. Commit and push to GitHub
5. Post link in MS Teams channel
