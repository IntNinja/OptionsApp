# activity_main.xml

``` xml
<?xml version="1.0" encoding="utf-8"?>  
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"  
    xmlns:app="http://schemas.android.com/apk/res-auto"  
    xmlns:tools="http://schemas.android.com/tools"  
    android:layout_width="match_parent"  
    android:layout_height="match_parent"  
    tools:context=".MainActivity">  
  
<androidx.appcompat.widget.Toolbar  
    android:id="@+id/toolbar"  
    android:layout_width="match_parent"  
    android:layout_height="?attr/actionBarSize"  
    android:background="?attr/colorPrimary"  
    app:popupTheme="@style/ThemeOverlay.AppCompat.Light"  
    app:title="Options Menu"  
    app:titleTextColor="@android:color/white"  
    app:theme="@style/ThemeOverlay.AppCompat.Dark.ActionBar"  
    app:navigationIcon="?android:attr/homeAsUpIndicator"  
    app:contentInsetStartWithNavigation="0dp"  
    app:layout_constraintTop_toTopOf="parent"  
    app:layout_constraintStart_toStartOf="parent"  
    app:layout_constraintEnd_toEndOf="parent" />  
  
<TextView  
    android:layout_width="wrap_content"  
    android:layout_height="wrap_content"  
    android:text="Hello World!"  
    app:layout_constraintBottom_toBottomOf="parent"  
    app:layout_constraintEnd_toEndOf="parent"  
    app:layout_constraintStart_toStartOf="parent"  
    app:layout_constraintTop_toTopOf="parent" />  
  
</androidx.constraintlayout.widget.ConstraintLayout>
```

# menu_main.xml
`Create Directory res/menu/`

``` xml
<menu xmlns:tools="http://schemas.android.com/tools"  
    xmlns:android="http://schemas.android.com/apk/res/android"  
    xmlns:app="http://schemas.android.com/apk/res-auto">  
  
    <item        android:id="@+id/item1"  
        android:title="Settings"  
        app:showAsAction="never"  
    />  
    <item        android:id="@+id/item2"  
        android:title="About"  
    />  
    <item        android:id="@+id/item3"  
        android:title="Logout" />  
</menu>
```

# MainActivity.Java

``` java
package com.example.myapplication;  
  
import android.os.Bundle;  
import android.view.Menu;  
import android.view.MenuItem;  
import android.widget.Toast;  
import androidx.annotation.NonNull;  
import androidx.appcompat.app.AppCompatActivity;  
import androidx.appcompat.widget.Toolbar;  
  
public class MainActivity extends AppCompatActivity {  
  
    @Override  
    protected void onCreate(Bundle savedInstanceState) {  
        super.onCreate(savedInstanceState);  
        setContentView(R.layout.activity_main);  
  
        Toolbar toolbar = findViewById(R.id.toolbar);  
        setSupportActionBar(toolbar);  
    }  
  
    @Override  
    public boolean onCreateOptionsMenu(Menu menu) {  
        getMenuInflater().inflate(R.menu.menu_main, menu);  
        return true;  
    }  
  
    @Override  
    public boolean onOptionsItemSelected(@NonNull MenuItem item) {  
        int id = item.getItemId();
        // switch case didn't work, so we use if else
        if (item.getItemId() == R.id.item1) {  
            Toast.makeText(getApplicationContext(), "Item 1 Selected", Toast.LENGTH_LONG).show();  
            return true;  
        } else if (item.getItemId() == R.id.item2) {  
            Toast.makeText(getApplicationContext(), "Item 2 Selected", Toast.LENGTH_LONG).show();  
            return true;  
        } else if (item.getItemId() == R.id.item3) {  
            Toast.makeText(getApplicationContext(), "Item 3 Selected", Toast.LENGTH_LONG).show();  
            return true;  
        } else {  
            return super.onOptionsItemSelected(item);  
        }  
    }  
}
```
