# 📝 Simple ToDo

A clean, minimal to-do list app built with Flutter. Add tasks, mark them as complete, and remove them with a satisfying swipe — all wrapped in a deep purple theme.

## ✨ Features

- **Add tasks** — Type a task into the input field and tap the `+` button to add it to your list.
- **Mark as complete** — Tap the checkbox next to a task to toggle its completed state. Completed tasks are shown with a strikethrough.
- **Swipe to delete** — Swipe a task left to reveal a delete action and remove it from the list.
- **Live list updates** — The list rebuilds instantly as tasks are added, checked off, or deleted, thanks to Flutter's `setState`.

## 📱 How It Works

The app is built around two main widgets:

### `HomePage`
The main screen and stateful heart of the app. It:
- Holds the current list of to-do items (each item is a `[name, isCompleted]` pair).
- Renders the list using a `ListView.builder`, generating a `TodoList` tile for every task.
- Provides a text field and floating action button for adding new tasks.
- Exposes three core actions:
    - `checkBoxChanged(index)` — toggles a task's completed status.
    - `saveNewTask()` — adds the text field's content as a new task and clears the input.
    - `deleteTask(index)` — removes a task from the list.

### `TodoList`
A stateless, reusable widget representing a single task row. It:
- Displays the task name and a checkbox.
- Applies a strikethrough style to the text when the task is marked complete.
- Wraps the task in a `Slidable` widget (from the `flutter_slidable` package), enabling the swipe-to-delete gesture with a stretch animation.

## 🎨 Design

The app uses a deep purple color palette throughout:
- App bar and floating elements in solid `Colors.deepPurple`.
- Background and input fields in lighter purple shades for contrast.
- Rounded corners (`BorderRadius.circular(15)`) on inputs, task cards, and swipe actions for a soft, modern look.

## 🛠️ Tech Stack

- **Framework:** [Flutter](https://flutter.dev)
- **Language:** Dart
- **Key Package:** [`flutter_slidable`](https://pub.dev/packages/flutter_slidable) — powers the swipe-to-delete interaction

## 📂 Project Structure

```
lib/
├── home_page.dart      # Main screen: state management, task list, input field
└── utils/
    └── todo_list.dart  # Reusable widget for rendering a single task tile
```

## 🚀 Getting Started

### Prerequisites
Make sure you have [Flutter installed](https://docs.flutter.dev/get-started/install) on your machine.

### Installation

1. Clone the repository:
   ```bash
   git clone <your-repo-url>
   cd To_Do_APP
   ```

2. Install dependencies:
   ```bash
   flutter pub get
   ```

3. Run the app:
   ```bash
   flutter run
   ```

## 📌 Roadmap / Ideas for Improvement

- Persist tasks locally (e.g. with `shared_preferences` or `sqflite`) so the list survives app restarts.
- Add task editing support.
- Add due dates and reminders.
- Add empty-state UI for when the list has no tasks.
- Prevent adding empty/blank tasks.

## 📚 Resources

If you're new to Flutter, these resources are a great starting point:

- [Learn Flutter](https://docs.flutter.dev/get-started/learn-flutter)
- [Write your first Flutter app](https://docs.flutter.dev/get-started/codelab)
- [Flutter learning resources](https://docs.flutter.dev/reference/learning-resources)
- [Flutter documentation](https://docs.flutter.dev/)

## 📄 License

This project is licensed under the [GNU General Public License v3.0](https://github.com/Ahmedsalim90/To_Do_app/blob/main/LICENSE).