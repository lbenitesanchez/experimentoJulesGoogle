# Task Manager Android App

A simple Android application for managing daily tasks. Users can add tasks, view them in a list, mark them as completed, and delete them.

## Features

- Add new tasks with descriptions.
- Display tasks in a scrollable list.
- Mark tasks as completed (visualized with a strikethrough).
- Delete tasks from the list.
- Simple and user-friendly interface.

## Prerequisites

- Android Studio (latest stable version recommended, e.g., Android Studio Giraffe | 2022.3.1 or newer)
- Java Development Kit (JDK) (usually bundled with Android Studio)
- An Android Virtual Device (AVD) set up in Android Studio, or a physical Android device (with USB debugging enabled).

## How to Build and Run

1.  **Clone the Repository or Download the Source Code:**
    ```bash
    # If you have git installed
    git clone <repository_url>
    cd <repository_directory>
    ```
    Alternatively, download the source code ZIP and extract it.

2.  **Open the Project in Android Studio:**
    *   Launch Android Studio.
    *   Click on "Open" (or "File" > "Open").
    *   Navigate to the directory where you cloned or extracted the project.
    *   Select the root project folder (the one containing `settings.gradle.kts` and `build.gradle.kts`) and click "OK".
    *   Android Studio will import the project and download any necessary Gradle dependencies. This might take a few minutes.

3.  **Build the Project:**
    *   Once the project is successfully synced, you can build it by selecting "Build" > "Make Project" from the Android Studio menu.
    *   Alternatively, Android Studio often builds the project automatically after syncing. Check the "Build" output window for any errors.

4.  **Run the App:**
    *   **Select a Deployment Target:**
        *   In the toolbar at the top of Android Studio, you'll see a dropdown menu for deployment targets (e.g., "Pixel 6 API 33").
        *   If you have an AVD configured, select it from the list. If not, you can create one via "Tools" > "Device Manager" > "Create device".
        *   If you have a physical Android device connected and USB debugging enabled, it should appear in this list. You might need to approve the computer's RSA key on your device.
    *   **Run the App:**
        *   Click the green "Run 'app'" button (the play icon) in the toolbar.
        *   Android Studio will build the app (if not already built), install it on the selected target (emulator or device), and then launch it.

5.  **Using the App:**
    *   Enter a task description in the input field.
    *   Click "Add Task" to add it to the list.
    *   Click the checkbox next to a task to mark it as completed.
    *   Click the "Delete" button next to a task to remove it.

## Code Structure

-   **`app/src/main/java/com/example/taskmanager/`**: Contains the Kotlin source code.
    -   `MainActivity.kt`: The main screen of the application.
    -   `Task.kt`: The data model for a task.
    -   `TaskAdapter.kt`: The RecyclerView adapter for displaying tasks.
-   **`app/src/main/res/`**: Contains application resources.
    -   `layout/activity_main.xml`: Layout for the main screen.
    -   `layout/item_task.xml`: Layout for individual task items in the list.
    -   `values/`: XML files for strings, colors, and themes.
-   **`app/src/main/AndroidManifest.xml`**: The application manifest file.
-   **Build Scripts (`.gradle.kts` files)**: Define how the application is built.

## Future Improvements

This basic Task Manager app can be extended with several features to make it more robust and user-friendly:

-   **Data Persistence:**
    -   **SharedPreferences:** For very simple persistence, suitable if tasks don't need complex querying.
    -   **Room Database:** A more robust solution for storing tasks locally, allowing for structured data, querying, and offline access. This would ensure tasks are saved even when the app is closed.
    -   **Jetpack DataStore:** A modern data storage solution that aims to replace SharedPreferences, offering support for Kotlin Coroutines and Flow.
-   **Edit Tasks:** Allow users to modify the description of existing tasks.
-   **Task Prioritization:** Implement a system to set task priorities (e.g., high, medium, low) and sort tasks accordingly.
-   **Due Dates & Reminders:** Add functionality to set due dates for tasks and integrate notifications as reminders.
-   **User Interface Enhancements:**
    -   Use Material Design components more extensively for a richer UI.
    -   Implement better visual cues for completed tasks (e.g., different background color).
    -   Add animations for adding/deleting tasks.
-   **Sorting and Filtering:** Allow users to sort tasks (e.g., by date, by completion status) and filter them (e.g., show only active tasks).
-   **Cloud Sync:** Integrate with a backend service (like Firebase) to sync tasks across multiple devices.
-   **Testing:** Add unit tests for business logic (e.g., in `TaskAdapter`, `MainActivity` view model if introduced) and UI tests (Espresso) for interactions.
