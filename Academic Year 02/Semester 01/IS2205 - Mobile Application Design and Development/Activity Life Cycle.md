# Understanding Tasks and the Back Stack

Android manages user experiences through **Tasks** and the **Back Stack**:

- **The Starting Point:** The device Home screen is the starting place for most tasks.
- **The Main Activity:** When an app is launched, the Android OS identifies the "main" activity using the **AndroidManifest.xml** file, specifically looking for the `<intent-filter>` with the `MAIN` action and `LAUNCHER` category.
- **The Back Stack (LIFO):** Activities operate on a "Last In, First Out" basis. When you start a new activity, it is **pushed** onto the top of the stack and takes focus. When you press the **Back** button, the current activity is **popped** (destroyed), and the previous activity is resumed.
- **Tasks:** A task is a cohesive unit of activities. If a task is abandoned (e.g., by pressing the Home button), it moves to the background, and the system retains the state of every activity in that task.

# The Activity Life Cycle States

An activity transitions through several states, managed by specific **callback methods** invoked by the Android OS.

- **onCreate()** **(Created State):** Fired when the system first creates the activity. This is where you initialize essential components, inflate the layout using `setContentView()`, and bind data.
- **onStart()** **(Started State):** Makes the activity **visible** to the user as it prepares to come to the foreground.
- **onResume()** **(Resumed State):** The activity is at the top of the stack, capturing all user input and becoming **interactive**. This is the "foreground" lifetime.
- **onPause()** **(Paused State):** The activity loses focus and is usually an indication that the user is leaving (e.g., tapping the Recents button). It may still be partially visible. **Crucial:** Do not perform heavy operations like database writes or network calls here, as they slow down the transition to the next activity.
- **onStop()** **(Stopped State):** The activity is no longer visible to the user. From here, the activity will either `onRestart()` to come back to the top or `onDestroy()` to terminate.
- **onRestart()****:** Called when an activity in the **Stopped** state is about to be restarted, restoring its state to before it was stopped.
- **onDestroy()** **(Destroyed State):** The final callback before the activity is terminated completely. It is used to ensure all resources are released.

# State Persistence and Useful Methods

Sometimes the system must kill an activity to reclaim memory. To handle this, Android provides methods to save and restore data:

- **onSaveInstanceState(Bundle)****:** Saves per-instance state (like text in a field) before the activity is **force killed** by the system.
- **onRestoreInstanceState(Bundle)****:** Called after `onStart()` to recover that saved data if the activity is re-initialized.
- **finish()****:** A method used to stop an activity programmatically when its task is done.

## Summary of Lifetimes

- **Entire Lifetime:** Between `onCreate()` and `onDestroy()`.
- **Visible Lifetime:** Between `onStart()` and `onStop()`.
- **Foreground (Interactive) Lifetime:** Between `onResume()` and `onPause()`.