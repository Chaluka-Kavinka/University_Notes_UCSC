# 1. What is an Intent?

An **Intent** is defined as a **"messenger"** that facilitates requesting an action from a different component at runtime. It is primarily used to:

- Start activities or services.
- Deliver broadcasts to **broadcast receivers**.
- Perform **late runtime binding** between code in different applications.

# 2. Types of Intents

Android uses three main categories of intents to handle different communication needs:

- **Explicit Intent:** Used when you have an **exactly defined target** component. This is common for navigating internally between activities in your own app.
- **Implicit Intent:** Specifies only a **generic action** to be performed. The Android system then resolves the request by finding a component that matches the criteria (like opening a web link in a browser).
- **Pending Intent:** A reference to a token maintained by the system that allows an external application to execute predefined actions on behalf of your app at a **future time**. A common use case is launching an app when a user clicks a **notification**.

# 3. Primary Information in an Intent

An intent typically contains several pieces of information used by the system to determine how to handle it:

- **Action:** A string describing the operation to perform, such as `ACTION_VIEW` (display data), `ACTION_SEND` (share data), or `ACTION_MAIN` (launch the main activity).
- **Category:** Used to classify the intent, such as `CATEGORY_LAUNCHER` (identifies intents that can launch a new app) or `CATEGORY_APP_BROWSER`.
- **Data and Type:** Specifies the **MIME type** of the data (e.g., `text/plain`, `image/jpeg`) and its URI.
- **Component:** Specifies the **explicit name** of a component class to use, which makes other resolution attributes optional.
- **Flag:** Provides a **hint to the system** on how to handle the intent, such as `FLAG_ACTIVITY_NEW_TASK` or `FLAG_ACTIVITY_CLEAR_TOP`.
- **Extras:** A collection of **additional information** added as key-value pairs using `putExtra()` and retrieved using methods like `getStringExtra()`.

# 4. Intent Filters

**Intent Filters** are declarations, usually found in the `AndroidManifest.xml`, that specify which intents a component can respond to.

- **Function:** They enable the handling of **implicit intents** by matching properties like Action, Category, and Data.
- **Matching Rules:** For a component to handle an intent, the intent's action must exactly match one in the filter, and all intent categories must be declared in the filter.

# 5. Broadcast Receivers

**Broadcast Receivers** follow a **publish-subscribe design** pattern.

- **Function:** They allow applications to receive and respond to broadcast messages from the **Android system** (like "boot completed" or "charging started") or from other apps (custom broadcasts).
- **Mechanism:** A **Publisher** sends an event through a system **Broker**, which then notifies all **Subscribers** (receivers) that have registered interest in that specific event.