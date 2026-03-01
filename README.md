# 🤖 BETATESTER Voice AI Agent
## APK Banane ka Poora Guide (Hindi)

---

## 📁 Is ZIP mein kya hai:

```
betatester-apk/
├── android-project/          ← Android Studio Project
│   ├── app/
│   │   ├── src/main/
│   │   │   ├── assets/
│   │   │   │   └── index.html      ← Main App (yahi chalti hai)
│   │   │   ├── java/
│   │   │   │   └── MainActivity.java
│   │   │   ├── res/values/
│   │   │   │   ├── strings.xml
│   │   │   │   └── styles.xml
│   │   │   └── AndroidManifest.xml
│   │   └── build.gradle
│   ├── build.gradle
│   └── settings.gradle
└── README.md (yeh file)
```

---

## 🚀 TARIKA 1: Android Studio se APK Banana (Recommended)

### Step 1 — Android Studio Download karo
👉 https://developer.android.com/studio
(Free hai, ~1GB download)

### Step 2 — ZIP Extract karo
- `betatester-apk.zip` ko extract karo
- `android-project` folder milega

### Step 3 — Android Studio mein Open karo
- Android Studio open karo
- **"Open"** click karo
- `android-project` folder select karo
- Wait karo (Gradle sync hoga ~2-3 min)

### Step 4 — APK Build karo
```
Menu: Build → Build Bundle(s) / APK(s) → Build APK(s)
```
- Wait karo ~3-5 minutes
- "APK Generated" notification aayegi
- **"locate"** click karo
- APK milega: `app/build/outputs/apk/debug/app-debug.apk`

### Step 5 — Phone mein Install karo
1. APK file WhatsApp/Email se phone pe bhejo
2. Phone mein open karo
3. **"Unknown Sources"** allow karo (Settings → Security)
4. Install karo ✅

---

## 🚀 TARIKA 2: Bina Computer ke — Online Build

### Option A: GitHub + GitHub Actions (Free)
1. GitHub account banao: https://github.com
2. New repository banao
3. `android-project` folder upload karo
4. `.github/workflows/build.yml` file banao:
```yaml
name: Build APK
on: [push]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - uses: actions/setup-java@v3
      with:
        java-version: '17'
        distribution: 'temurin'
    - name: Build APK
      run: |
        cd android-project
        chmod +x gradlew
        ./gradlew assembleDebug
    - uses: actions/upload-artifact@v3
      with:
        name: BETATESTER-APK
        path: android-project/app/build/outputs/apk/debug/app-debug.apk
```
5. Push karo → Automatically APK build hogi
6. Actions tab → Download APK

---

## 📱 TARIKA 3: Seedha HTML File (Sabse Aasan!)

**`betatester.html`** file directly phone ke browser mein kholein:

### Android Chrome mein:
1. File phone pe save karo (WhatsApp ya email se)
2. Files app mein dhundho
3. Chrome se open karo
4. Address bar ke 3-dot menu → **"Add to Home Screen"**
5. Done! ✅ App icon home screen pe aa jayega

### iPhone Safari mein:
1. File open karo Safari mein
2. Share button (box with arrow) → **"Add to Home Screen"**

---

## 🎤 App Kaise Use Karein:

| Action | Kya Bolein |
|--------|------------|
| Unlock | "ek" "do" "teen" "char" |
| Wake   | "Hey BETATESTER" |
| Google | "Google pe cats search karo" |
| WhatsApp | "WhatsApp message bhejo" |
| Email  | "Email send karo" |
| Call   | "Call karo" |
| Camera | "Camera on karo" |
| Music  | "Music bajao" |
| Lock   | "Phone lock karo" |

**Default PIN: 1-2-3-4** (Voice: "ek do teen char")

---

## ⚠️ Zaruri Jaankari:

- **Microphone Permission:** Install ke baad "Allow" zaroor karein
- **Chrome Browser:** Best kaam karta hai Voice ke liye
- **Internet:** Google Search ke liye zaruri hai
- **Android Version:** 5.0+ (Lollipop) support karta hai

---

## 🔧 PIN Change Karna:

`index.html` file mein line dhundho:
```javascript
const CORRECT_PIN = ["1","2","3","4"];
```
Ise badlo, jaise:
```javascript
const CORRECT_PIN = ["9","8","7","6"];
```

---

Made with ❤️ by BETATESTER Voice AI Agent
