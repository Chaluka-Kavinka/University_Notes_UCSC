# 1. Data Storage Strategies

Android provides different ways to store data depending on whether the data is private to your app or should be shareable with others:

- **App-Specific Storage:** Used for files meant only for your app's use.
- **Shared Storage:** Designed for files that your app intends to share with other apps, such as media (photos, audio, video) and documents.
- **Preferences:** Used to store small amounts of primitive data in key-value pairs (Shared Preferences).
- **Databases:** Used to store structured data in a private database.

# 2. Shared Storage and APIs

Shared storage allows files to remain on the device even after your app is uninstalled.

- **MediaStore API:** This is the standard way to access public directories for photos, audio, and video.
- **Storage Access Framework (SAF):** This API is used to access other public documents, such as PDF or EPUB files.
- **Permissions:** Before Android 13, apps typically required `READ_EXTERNAL_STORAGE` and `WRITE_EXTERNAL_STORAGE` permissions to access these shared files.

# 3. Databases and SQL

For complex, structured data, Android uses relational databases.

- **Database Structure:** Data is organized into **Tables**, which consist of **Rows** (individual records) and **Columns** (specific data fields like name, age, or email).
- **SQL (Structured Query Language):** This is the standard language used to interact with these databases. Key operations include:
    - **Create:** Making new tables.
    - **Query:** Searching for specific data.
    - **Insert:** Adding new data records.
    - **Update/Delete:** Modifying or removing existing data.

# 4. SQLite and the Room Persistence Library

- **SQLite:** Android includes a built-in implementation of **SQLite**, a lightweight SQL database engine.
- **Room Library:** While you can use SQLite directly, modern Android development favors the **Room Persistence Library**. It provides an abstraction layer over SQLite to allow for more robust database access while leveraging the full power of SQLite.
- **Core Components of Room:**
    - **Entities:** Represent tables in your database.
    - **DAO (Data Access Object):** Contains the methods used for accessing the database (e.g., using a DAO to insert a new object like a "Color" into the database).
    - **Database:** Serves as the main access point for the connection to your app's persisted data.