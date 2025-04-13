# llamaedit
LLamaEdit is a code editor with AI autocompletion powered by LLamaCPP and CodeMirror. You must have llama-server running with a model loaded, I suggest deepcoder 14b or deepseek coder v2 lite. I only have a 4gb card though.
Should work on any computer or operating system with a fairly modern web browser.
The file operations have keyboard commands, mouse over to see them. Usage shluld be self-explanatory, alt+backspc to get suggested autocomplete, tab to accept, esc to cancel.

# LLamaEdit User Documentation

## 1. Introduction

LLamaEdit is a web-based code editor featuring syntax highlighting, file management, find & replace, theme customization, and AI-powered code completion via a local Llama.cpp server.

## 2. Interface Overview

*   **Navbar:** Displays the application title ("LLamaEdit") and the "Cycle Theme" button.
*   **Toolbar:** Contains buttons for common file operations and access to Find/Replace.
    *   **New:** Create a new file.
    *   **Open:** Open a file from your computer.
    *   **Save:** Save the current file (enabled for unsaved files).
    *   **Save As:** Save the current file with a new name or location.
    *   **Find/Replace:** Toggle the Find/Replace bar.
    *   **Language Select:** Manually change the syntax highlighting for the current file.
*   **Find/Replace Bar:** (Appears below the toolbar when activated) Allows searching and replacing text within the current file.
*   **Sidebar:**
    *   Lists currently open files.
    *   The active file is highlighted.
    *   An asterisk (`*`) next to a filename indicates unsaved changes.
    *   Click a filename to switch to that file.
    *   Click the `×` button next to a filename to close it (you'll be prompted if there are unsaved changes).
*   **Editor Area:** The main area where you write and edit code, powered by CodeMirror.
*   **Status Bar:** Located at the bottom.
    *   **Left:** Shows the name of the currently open file and its save status.
    *   **Center:** Displays status messages (e.g., "Saved", "AI thinking...", error messages).
    *   **Right:** Shows the current cursor position (Line number, Column number).

## 3. Core Features

### 3.1. File Management

*   **New File (`Ctrl+N` or "New" button):** Opens a dialog to enter a filename and select the language. Click "Create".
*   **Open File (`Ctrl+O` or "Open" button):** Uses your browser's file picker to select a file. If a file with the same name is already open, you may be prompted to reload it.
*   **Save File (`Ctrl+S` or "Save" button):** Saves changes to the current file. Uses the File System Access API if available (prompts for permission on first save), otherwise triggers a download. Enabled only when there are unsaved changes.
*   **Save As (`Ctrl+Shift+S` or "Save As" button):** Opens a dialog to specify a new filename. Saves the file under the new name.
*   **Switching Files:** Click the desired filename in the sidebar.
*   **Closing Files:** Click the `×` button next to the filename in the sidebar.

### 3.2. Editing

*   Standard text editing features.
*   Syntax highlighting based on file extension or manual selection via the Language dropdown.
*   Line numbers.
*   Automatic bracket matching and closing.

### 3.3. AI Code Completion

*   **Trigger:** Press `Alt+\` (Alt + Backslash) in the editor.
*   **Process:** The text before your cursor is sent to your configured Llama.cpp server.
*   **Suggestion:** If the AI provides a completion, it will appear as greyed-out, italicized text directly after your cursor.
*   **Accept:** Press `Tab` to insert the suggestion.
*   **Reject:** Press `Esc` or simply continue typing to dismiss the suggestion.
*   **Status:** The status bar indicates when the AI is processing ("AI thinking...") or displays errors.

**Note:** AI Completion requires a running Llama.cpp server accessible at the URL configured in the `LLAMA_API_URL` variable within the application's code (`http://localhost:8080/completion` by default).

### 3.4. Find & Replace

*   **Open:** Click the "Find/Replace" button or press `Ctrl+F`.
*   **Find:** Enter text in the "Find..." input.
    *   Press `Enter` or click "Next" to find the next occurrence.
    *   Press `Shift+Enter` or click "Prev" to find the previous occurrence.
*   **Replace:** Enter replacement text in the "Replace with..." input.
    *   Click "Replace" to replace the currently highlighted match and move to the next.
    *   Click "Replace All" to replace all occurrences in the file.
*   **Close:** Click the `×` button on the Find/Replace bar or press `Esc` while the bar has focus.

### 3.5. Customization

*   **Themes:** Click the "Cycle Theme" button in the navbar to rotate through available editor themes (e.g., Dracula, Material, Solarized Light/Dark, etc.).

## 4. Keyboard Shortcuts

*   **New File:** `Ctrl+N`
*   **Open File:** `Ctrl+O`
*   **Save File:** `Ctrl+S`
*   **Save As:** `Ctrl+Shift+S`
*   **Find:** `Ctrl+F`
*   **Find Next:** `Enter` (in Find input)
*   **Find Previous:** `Shift+Enter` (in Find input)
*   **Replace:** `Ctrl+H` (Opens Find/Replace with focus on Replace input - *standard CodeMirror binding, may vary slightly*)
*   **Trigger AI Completion:** `Alt+\`
*   **Accept AI Suggestion:** `Tab`
*   **Dismiss AI Suggestion / Close Find/Replace / Close Modals:** `Esc`

## 5. Important Notes

*   **Unsaved Changes:** The application will warn you if you try to close a file with unsaved changes or leave the page with unsaved files.
*   **AI Server:** Ensure your local Llama.cpp server is running and accessible at the configured `LLAMA_API_URL` for AI features to work.
