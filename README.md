# llamaedit
LLamaEdit is a code editor with AI autocompletion powered by LLamaCPP and CodeMirror. You must have llama-server running with a model loaded, I suggest deepcoder 14b or deepseek coder v2 lite. I only have a 4gb card though.
Should work on any computer or operating system with a fairly modern web browser.
The file operations have keyboard commands, mouse over to see them. Usage should be self-explanatory, alt+backspc to get suggested autocomplete, tab to accept, esc to cancel.


# LLamaEdit User Guide

LLamaEdit is a web-based code editor featuring syntax highlighting, linting, theme customization, and AI-powered code completion via a local Llama.cpp server.

## Getting Started

*   **New File**:
    *   Click `File > New File` or the `New` button on the toolbar (`Ctrl+N`).
    *   Enter a `File Name` (extension helps detect language) and select the `Language` in the modal. Click `Create`.
*   **Open File**:
    *   Click `File > Open File...` or the `Open` button on the toolbar (`Ctrl+O`).
    *   Select a file from your computer using the file picker.
    *   If a file with the same name is already open, you'll be prompted to reload it.
*   **Saving Files**:
    *   An asterisk (`*`) next to the filename (in the sidebar and status bar) indicates unsaved changes.
    *   `File > Save` or the `Save` button on the toolbar (`Ctrl+S`) saves the current file.
        *   If the file hasn't been saved before (or uses the legacy download method), it will act like "Save As".
    *   `File > Save As...` (`Ctrl+Shift+S`) always prompts you to choose a name and location for the file.

## Core Editing Features

*   **Syntax Highlighting**: Automatically applied based on the detected file language (from extension or manual selection).
*   **Linting (Error/Warning Checking)**: Automatically runs for supported languages (JS, CSS, HTML, JSON, YAML). Errors/warnings are marked in the left gutter; hover over them for details.
*   **AI Code Completion**:
    *   Press `Alt+\` to request a code completion suggestion from the connected Llama.cpp server based on the preceding code.
    *   The suggestion appears as grayed-out text.
    *   Press `Tab` to accept the suggestion.
    *   Press `Esc` or continue typing to reject the suggestion.

## Finding and Replacing Text

*   Open the Find/Replace bar via `Edit > Find/Replace...`, the `Find` button on the toolbar, or `Ctrl+F`.
*   **Find Input**: Type your search query here.
    *   Press `Enter` to find the next match.
    *   Press `Shift+Enter` to find the previous match.
*   **Replace Input**: Type the text to replace matches with.
*   **Buttons**:
    *   `Prev`/`Next`: Navigate through matches.
    *   `Replace`: Replace the currently selected match and find the next one.
    *   `Replace All`: Replace all occurrences in the file.
    *   `×` (Close): Hides the Find/Replace bar (`Esc` also works).

## File Management (Sidebar)

*   The left sidebar lists all open files.
*   The currently active file is highlighted.
*   An asterisk (`*`) indicates unsaved changes for a file.
*   Click a filename to switch to that file.
*   Click the `×` button next to a filename to close that file (`Ctrl+W` also closes the current file). You'll be prompted if there are unsaved changes.

## Customization

*   **Themes**: Change the editor and UI appearance via the `Theme` menu. Select from Light and Dark options.
*   **Language**:
    *   The language is usually auto-detected from the filename.
    *   Manually change the language for the current file via `View > Language > [Select Language]`.
    *   The current language is displayed in the status bar.
*   **View Options**:
    *   `View > Toggle Line Numbers`: Show/hide line numbers in the gutter.
    *   `View > Toggle Line Wrapping`: Enable/disable text wrapping for long lines.

## Status Bar

Located at the bottom, it displays:

*   **Left**: Current `File Name` (with `*` if unsaved).
*   **Middle**: Status messages (Ready, Saving, AI status, Errors).
*   **Right**: Current `Language`, Cursor `Line` and `Column` position.

## Keyboard Shortcuts

*   **File**:
    *   `Ctrl+N`: New File
    *   `Ctrl+O`: Open File
    *   `Ctrl+S`: Save File
    *   `Ctrl+Shift+S`: Save File As
    *   `Ctrl+W`: Close Current File
*   **Edit**:
    *   `Ctrl+Z`: Undo
    *   `Ctrl+Y` / `Shift+Cmd+Z` (Mac): Redo
    *   `Ctrl+F`: Find/Replace
*   **AI**:
    *   `Alt+\`: Trigger AI Completion
    *   `Tab`: Accept AI Suggestion
    *   `Esc`: Reject AI Suggestion / Close Find Bar / Close Modals
*   **General**:
    *   `Ctrl+Space`: Trigger basic code hints (if available for the language).
