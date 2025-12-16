```markdown
<div align="center">

  <img src="app/src/main/res/drawable/ic_guy.png" alt="Logo" width="100" height="100" style="border-radius: 20%;">
  
  # Student Run 🏃‍♂️🎓
  
  **An Android Survival Game demonstrating MVC Architecture & Logic Separation.**
  
  <p>
    <img src="https://img.shields.io/badge/Platform-Android-3DDC84?style=flat&logo=android&logoColor=white" alt="Android" />
    <img src="https://img.shields.io/badge/Language-Kotlin-7F52FF?style=flat&logo=kotlin&logoColor=white" alt="Kotlin" />
    <img src="https://img.shields.io/badge/Architecture-MVC-blue?style=flat" alt="MVC" />
    <img src="https://img.shields.io/badge/IDE-Android%20Studio-3DDC84?style=flat&logo=android-studio&logoColor=white" alt="Android Studio" />
  </p>
</div>

---

## 📖 About The Project
**Student Run** is a dynamic arcade game where logic meets reflexes. The project was built to showcase **clean code principles** in Android development, specifically focusing on decoupling the Game Logic from the UI.

The player controls a student navigating a 3-lane grid, dodging exams and collecting grades, with speed increasing over time.

---

## 📱 Gameplay Demo

<div align="center">
  <video src="https://github.com/user-attachments/assets/78cf0727-a4d5-4ee7-82cf-a5a911ae75f9" width="400" />
</div>

> *Tip: Ensure volume is up to hear the collision effects!*

---

## 🚀 Key Features

| Feature | Description |
| :--- | :--- |
| **🧠 Smart Logic Engine** | A dedicated `GameManager` class that handles the 7x3 matrix logic, completely separated from the View. |
| **⚡ Custom Game Loop** | Uses `Handler` & `Runnable` for a precise 500ms tick-rate, independent of UI frame-rate. |
| **📳 Haptic Feedback** | Integrated Vibrator service to provide tactile feedback upon collisions. |
| **🔄 Lifecycle Aware** | Automatically pauses/resumes game state when the app goes to the background. |

---

## 🛠️ Architecture & Tech Stack

The project follows the **MVC (Model-View-Controller)** principles:

### 🎨 View (UI Layer)
* **`GameActivity`**: Updates the UI based on matrix changes.
* **`HomeActivity`**: Simple entry point using ViewBinding.
* **`ResultActivity`**: Displays final score and high-score logic.

### 🧠 Controller & Model (Logic Layer)
* **`GameManager`**: The "Brain". Manages the grid state (`0` for empty, `1` for player, `2` for obstacle).
* **`Player`**: Data class holding position and lives.
* **`GameSymbol`**: Enum mapping logic states to UI drawables.

```kotlin
// Example: Decoupled Logic
fun movePlayer(direction: Direction) {
    if (canMove(direction)) {
        player.position += direction.offset
        checkForCollision()
    }
}

```

---

##📂 Project Structure```text
app/src/main/java/com/example/studentrun
├── 🎮 activity      # UI Controllers (Activities)
├── 🧠 logic         # Pure Game Logic (Managers)
├── 📦 model         # Data Classes (Player, Symbol)
└── ⚙️ utilities     # Constants & Extensions

```

---

##👨‍💻 Created By**Ofek Fanian** *Built as part of an Android Development Course Assignmen
