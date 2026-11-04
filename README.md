# DroidCafe — Android Intent Navigation & Order Flow Architecture

[![Android CI](https://github.com/luminariadev/droidcafe/actions/workflows/ci.yml/badge.svg)](https://github.com/luminariadev/droidcafe/actions/workflows/ci.yml)
[![Kotlin](https://img.shields.io/badge/Kotlin-1.9+-7F52FF?logo=kotlin&logoColor=white)](https://kotlinlang.org/)
[![Android](https://img.shields.io/badge/Platform-Android-3DDC84?logo=android&logoColor=white)](https://developer.android.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A native Android application demonstrating explicit multi-activity navigation, intent payload transfer, and interactive delivery selection menus in Kotlin.

---

## Architectural Workflow

```
[MainActivity] (Catalog View)
       │
       ├─ Click on Dessert Item (Donut / Ice Cream / Froyo)
       │    └─ Display confirmation Toast
       │
       └─ Click Floating Action Button (Cart)
            │
            ▼ (Explicit Intent with Payload)
[OrderActivity] (Checkout View)
       │
       ├─ Capture Customer Inputs (Name, Address, Phone, Note)
       │
       └─ Delivery Options RadioGroup:
            ├─ Same day messenger service
            ├─ Next day ground delivery
            └─ Pick up in store
```

---

## Project Structure

```
droidcafe/
├── .github/
│   └── workflows/
│       └── ci.yml              # Gradle test & build validation pipeline
├── app/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/           # MainActivity & OrderActivity controllers
│   │   │   ├── res/            # Menu layouts, drawables, strings
│   │   │   └── AndroidManifest.xml
│   │   └── test/               # Local unit test suites
│   └── build.gradle.kts
├── gradle/
├── .gitignore
├── LICENSE
└── README.md
```

---

## Build & Installation

### Prerequisites

* Android Studio Hedgehog (2023.1.1) or later
* JDK 17
* Android SDK (API 34)

### Clone & Assemble Debug APK

```bash
git clone https://github.com/luminariadev/droidcafe.git
cd droidcafe
./gradlew assembleDebug
```

---

## Testing

Execute local unit test suites:

```bash
./gradlew test
```

Continuous integration runs automated linting and unit tests via GitHub Actions.

---

## License

Distributed under the [MIT](LICENSE) License.
