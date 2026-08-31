# 1. Flutter Storage Strategies

Flutter offers multiple ways to persist data, often managed through **Enums** to create clean, switchable code for different data sources.

- **SharedPreferences:** Used for simple key-value pairs, typically for **app configurations** (e.g., saving the user's preferred storage method).
- **SQLite (sqflite):** A relational database used for **structured local data** requiring complex queries.
- **Hive:** Mentioned as an efficient **in-memory** or local storage alternative.
- **Firebase:** A cloud-based platform used for **remote data persistence** and real-time synchronization.

# 2. Dart Concurrency: Future, async, and await

Because data storage operations (like reading from a database) take time, they must be handled with **concurrency** to keep the UI responsive.

- **Future** **(Class):** Represents a value or error that will be available at some point in the future.
- **async** **(Keyword):** Marks a method to run asynchronously, allowing it to perform background tasks.
- **await** **(Keyword):** Pauses the execution of a specific block until a `Future` returns a value, ensuring the app remains interactive in the meantime.

# 3. Managing Data with StatefulWidget

Persistence in Flutter is closely tied to the **StatefulWidget** lifecycle to ensure data is loaded correctly before the user sees the UI.

- **initState()****:** This method is called exactly once when the widget is created, **before the UI is built**. It is the ideal place to load configurations (`_loadConfig()`) or initial data (`_loadCounter()`).
- **setState()****:** Once an asynchronous storage task completes, `setState()` is called to notify the framework that the data has changed, triggering a **UI rebuild** to display the new values.

# 4. Implementation: SQLite (sqflite)

Structured local storage is implemented using the `sqflite` and `path` packages.

- **Database Instance:** Use a **private method** (`_getDatabase()`) to ensure a single instance of the database object is maintained per file path.
- **Table Creation:** Use the `onCreate` callback to execute SQL commands like `CREATE TABLE` when the database is first initialized.
- **CRUD Operations:** Operations are marked as `async` and use `await` to interact with the database.
    - **Querying:** `db.query('table_name', where: 'id = ?', ...)`.
    - **Updating:** `db.update('table_name', values, where: 'id = ?', ...)`.

# 5. Implementation: Firebase Integration

Connecting a Flutter app to **Firebase** requires specific configuration steps across the web console and the local project.

- **Firebase Console:** Create a project in the web console and register your specific Android/Web apps to generate connection parameters.
- **Android Configuration:**
    - Place the **google-services.json** file in the appropriate project directory.
    - Add the **Google Services dependency** to your Gradle build files.
    - Declare the **Internet permission** (`android.permission.INTERNET`) in the `AndroidManifest.xml`.

## Example: Clean Code with Enums

Using an **Enum** allows you to map code logic, stored values, and display names in a centralized way:

```kotlin
enum DataSource {
  sharedprefs(0, "SharedPrefs"),
  sqlite(1, "SQLite DB"),
  hive(2, "In Memory"),
  firebase(3, "FireBase");

  final int num;
  final String str;
  const DataSource(this.num, this.str);
}
```

This enables a **cleaner implementation** when building UI menus (like a `PopupMenuButton`) to switch between persistence types.