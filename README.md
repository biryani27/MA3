# MA3

MAINACTIVITY.JAVA
package com.example.eventlistener;
import androidx.appcompat.app.AppCompatActivity;
import androidx.core.view.GestureDetectorCompat;
import android.os.Bundle;
import android.view.GestureDetector;
import android.view.MotionEvent;
import android.widget.Toast;
import android.os.Bundle;
public class MainActivity extends AppCompatActivity {
    private GestureDetectorCompat mGestureDetector;
    private class GestureListener extends
            GestureDetector.SimpleOnGestureListener {
        @Override
        public boolean onSingleTapConfirmed(MotionEvent e) {

            Toast.makeText(MainActivity.this,"onSingleTapConfirmed",Toast.LENGTH_SHORT)
                    .show();
            setContentView(R.layout.layoutone);
            return super.onSingleTapConfirmed(e);
        }
        @Override
        public boolean onDoubleTap(MotionEvent e) {

            Toast.makeText(MainActivity.this,"onDoubleTap",Toast.LENGTH_SHORT).show();
            setContentView(R.layout.layouttwo);
            return super.onDoubleTap(e);
        }
    }
    public boolean onTouchEvent(MotionEvent event) {
        mGestureDetector.onTouchEvent(event);
        return super.onTouchEvent(event);
    }
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        mGestureDetector = new GestureDetectorCompat(this, new
                GestureListener());
    }
}


Activity_main.xml

<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello World!"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>

layouttwo.xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:orientation="vertical" android:layout_height="wrap_content">
    <Button
        android:id="@+id/button2" android:layout_width="match_parent"
        android:layout_height="wrap_content" android:layout_weight="1"
        android:text="Button" />
    <Button android:id="@+id/button"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" android:layout_weight="1"
        android:text="Button" />
</LinearLayout>


layoutone.xml

<?xml version="1.0" encoding="utf-8"?>
<TableLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:stretchColumns="1">
    <TableRow>
        <TextView
            android:text="Open"
            android:padding="3dip" />
        <TextView
            android:text="Short cut"
            android:gravity="right"
            android:padding="3dip" />
    </TableRow>
    <TableRow>
        <TextView
            android:text="SAVE"
            android:padding="3dip" />
        <TextView
            android:text="SAve Short Cut"
            android:gravity="right"
            android:padding="3dip" />
    </TableRow>
</TableLayout>

