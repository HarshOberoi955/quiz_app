# GNE Pro Coding Assessment Platform

A fully functional, browser-based C++ coding assessment portal. It simulates a professional enterprise coding environment like LeetCode or HackerRank, running entirely on the client side.

## 🚀 Features
* **Live C++ Execution:** Compiles and runs C++ code in real-time using the Wandbox API.
* **Dynamic XML Parsing:** Automatically reads and generates the UI from a Moodle `questions.xml` export.
* **Professional IDE:** Split-pane layout utilizing the Ace Editor with syntax highlighting and theme support.
* **Strict Proctoring Mode:** Anti-cheat mechanisms that detect tab-switching and disable copy-pasting.
* **Advanced Auto-Grader:** Automatically evaluates student code against hidden test cases with a forgiving whitespace parser.
* **Crash Recovery:** Auto-saves code keystroke-by-keystroke to the browser's local storage.

## 📝 Prerequisites: Generating the Questions
This platform is designed to seamlessly integrate with Moodle's CodeRunner question type. **Before running this app, you must generate your own question bank.**

1. Log into your Moodle Administrator dashboard.
2. Create your coding questions using the **CodeRunner** plugin. Ensure you define the required Test Cases (Inputs and Expected Outputs).
3. Export the question category as a **Moodle XML format** file.
4. Rename the downloaded file to `questions.xml` and place it in the root directory of this project. 
*(Note: `questions.xml` is included in the `.gitignore` to prevent leaking private exam data).*

## 🛠️ How to Run
Because this platform uses the `fetch()` API to read the `questions.xml` file, it must be run through a local web server (it cannot be opened directly via `file://`).

1. Clone this repository.
2. Ensure your generated `questions.xml` file is in the root directory.
3. Start a local web server. For example, using Python:
   ```bash
   python -m http.server 8000