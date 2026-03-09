# Unlock the App

Unlock the App is a JavaFX application that uses image classification to generate and validate a PIN for unlocking purposes. The application captures live camera feed, processes the images using a TensorFlow model, and updates the GUI accordingly.

## 🔎 Existing Code

### Unlock.java

The `Unlock` class controls the locking and unlocking flow of the application.  
It processes predicted classes from the TensorFlow model, updates the user PIN, displays feedback messages, and manages the timeline responsible for updating predictions and UI responses.

**Implemented Features:**

* Handles prediction results from the image classification model.
* Updates the user PIN dynamically based on predicted classes.
* Manages the unlock validation process.
* Controls the timeline responsible for periodic prediction updates.

---

### LockScene.java

The `LockScene` class represents the locked state of the application.  
It displays the camera feed, loading animations, and feedback messages while the user is entering the PIN using image predictions.

**Implemented Features:**

* Displays the live camera feed for gesture/image recognition.
* Shows loading animations during initialization.
* Provides visual feedback while the user PIN is being entered.
* Maintains the locked interface until the correct PIN is entered.

---

### MainScene.java

The `MainScene` class initializes the main user interface and manages core UI components used during the unlock process.

**Implemented Features:**

* Displays validation messages to inform users about the unlock status.
* Provides buttons and UI components for interaction.
* Updates UI elements dynamically based on application state.

---

### Loading.java

The `Loading` class manages loading animations and labels that appear while the application initializes the camera or processes classification results.

**Implemented Features:**

* Displays loading animations during system initialization.
* Updates loading labels to inform the user about the current status.

---

## ✅ Implemented Logic: AppLogic.java

The `AppLogic` class manages the core logic of the application, including PIN generation, PIN validation, and processing user input based on predicted classes from the image classification model.

### Implemented Methods

#### `createUserPin(String predictedClass)`

Appends the predicted digit to the current user PIN based on the predicted class from the model and returns the updated PIN.

#### `checkPinLength()`

Checks whether the user PIN has reached the required length (4 digits).

Returns:
* `true` if the PIN length is 4  
* `false` otherwise

#### `getPinStatus(String userPin)`

Compares the user PIN with the stored generated PIN.

Returns:
* `"correct"` if the PIN matches  
* `"incorrect"` if the PIN does not match

#### `createRandomPin()`

Generates a random 4-digit PIN between **1000 and 9999** that will be used as the authentication PIN.

Returns the generated PIN as a string.

---

## ⚙️ Technologies Used

* Java
* JavaFX
* TensorFlow
* Teachable Machine
* Webcam image capture
