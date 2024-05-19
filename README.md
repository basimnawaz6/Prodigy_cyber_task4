This script is a simple keylogger written in C++ for Windows. Here's how it works:

1. **Includes and Namespace**:
    - It includes necessary headers like `iostream`, `windows.h`, `winuser.h`, `fstream`, and `csignal`.
    - Uses the standard namespace to simplify code syntax.

2. **Function Declarations and Global Variable**:
    - Declares two functions, `logKeys()` and `signalHandler(int signal)`.
    - Uses a global boolean variable `shouldTerminate` to control the termination of the keylogger.

3. **Main Function**:
    - Sets up a signal handler for the `SIGINT` signal (triggered by pressing Ctrl+C).
    - Prints a message indicating that the keylogger is running.
    - Calls `logKeys()` to start logging keystrokes.
    - Returns 0 to end the program.

4. **Signal Handler Function**:
    - `signalHandler(int signal)`: Sets the `shouldTerminate` flag to `true` when a `SIGINT` signal is received, indicating the program should stop.

5. **Keylogging Function**:
    - `logKeys()`: Contains the logic to capture and log keystrokes.
    - Iterates through possible key values using a loop.
    - Checks if a key was pressed using `GetAsyncKeyState`.
    - Logs the key press to a file (`Record.txt`).
    - Handles special keys like Backspace, Enter, Space, and Delete.
    - Uses a small delay (`Sleep(10)`) to reduce CPU usage.

### How to Use the Keylogger

1. **Run the Program**:
    - Compile and run the keylogger program.

2. **Logging Keystrokes**:
    - The program will start capturing keystrokes and logging them to `Record.txt`.
    - Special keys like Backspace, Enter, Space, and Delete are logged with readable tags.

3. **Terminating the Program**:
    - Press Ctrl+C to gracefully terminate the keylogger.
    - The program will stop logging and exit cleanly.

4. **Viewing the Log**:
    - Open `Record.txt` to view the logged keystrokes.

### Additional Notes

- **Security Implications**: This keylogger is for educational purposes only. Unauthorized use of keyloggers is illegal and unethical.
- **Performance**: The program includes a `Sleep(10)` call to ensure it does not consume excessive CPU resources.
- **File Management**: Regularly monitor the size of `Record.txt` as it can grow large over time.
