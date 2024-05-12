# Login-Page-in-Android-Studio

## ALGORITHM : 

1. Define a custom shape for EditText fields with rounded corners and a purple border.
2. Design a login screen layout using a CardView to group login elements.
3. Customize EditText fields with icons, hints, and padding for user input.
4. Include a TextView for signing up if users are not registered yet.
5. Initialize views in MainActivity to handle user interactions.
6. Implement login functionality to verify entered credentials.
7. Display appropriate toast messages for successful or failed login attempts.


## CODE

# CUSTOM_TEXT.AML:
```XML
<?xml version="1.0" encoding="utf-8"?>
<shape
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:shape="rectangle">

    <stroke
        android:width="3dp"
        android:color="@color/purple"/>

    <corners
        android:radius="20dp"/>

</shape>
```

# ACTIVITY_MAIN.XML
```XML
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:background="@drawable/back"
    tools:context=".MainActivity">

    <androidx.cardview.widget.CardView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="30dp"
        app:cardCornerRadius="20dp"
        app:cardElevation="20dp"
        android:background="@drawable/custom_edittext">

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_gravity="center_horizontal"
            android:orientation="vertical"
            android:padding="24dp">


            <TextView
                android:id="@+id/loginText"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:text="Login"
                android:textAlignment="center"
                android:textColor="@color/purple"
                android:textSize="34sp"
                android:textStyle="bold" />

            <EditText
                android:id="@+id/username"
                android:layout_width="match_parent"
                android:layout_height="50dp"
                android:layout_marginTop="40dp"
                android:background="@drawable/custom_edittext"
                android:drawableLeft="@drawable/baseline_person_24"
                android:drawablePadding="8dp"
                android:hint="Username"
                android:padding="8dp"
                android:textColor="@color/black"
                android:textColorHighlight="@color/cardview_dark_background" />

            <EditText
                android:id="@+id/password"
                android:layout_width="match_parent"
                android:layout_height="50dp"
                android:layout_marginTop="20dp"
                android:background="@drawable/custom_edittext"
                android:drawableLeft="@drawable/baseline_lock_24"
                android:drawablePadding="8dp"
                android:hint="Password"
                android:inputType="textPassword"
                android:padding="8dp"
                android:textColor="@color/black"
                android:textColorHighlight="@color/cardview_dark_background"/>

            <Button
                android:layout_width="match_parent"
                android:layout_height="60dp"
                android:id="@+id/loginButton1"
                android:text="Login"
                android:textSize="18sp"
                android:layout_margin="30dp"
                android:backgroundTint="@color/purple"
                app:cornerRadius = "20dp"/>

        </LinearLayout>

    </androidx.cardview.widget.CardView>

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:padding="8dp"
        android:text="Not Yet Registered ? Signup Now"
        android:textAlignment="center"
        android:textSize="14sp"
        android:id="@+id/signupText"
        android:textColor="@color/black"
        android:layout_marginTop="20dp"/>

</LinearLayout>
```

# MAIN_ACTIVITY.JAVA
```JAVA
package com.example.projectmodel;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

import androidx.activity.EdgeToEdge;
import androidx.appcompat.app.AppCompatActivity;
import androidx.core.graphics.Insets;
import androidx.core.view.ViewCompat;
import androidx.core.view.WindowInsetsCompat;

public class MainActivity extends AppCompatActivity {
    EditText username;
    EditText password;
    Button loginButton;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        EdgeToEdge.enable(this);
        setContentView(R.layout.activity_main);

        username = findViewById(R.id.username);
        password = findViewById(R.id.password);
        loginButton = findViewById(R.id.loginButton1);

        loginButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                if(username.getText().toString().equals("user") && password.getText().toString().equals("1234")){
                    Toast.makeText(MainActivity.this,"Login Successful",Toast.LENGTH_LONG).show();
                }
                else{
                    Toast.makeText(MainActivity.this,"Login Failed",Toast.LENGTH_LONG).show();
                }
            }
        });
    }
}
```


## OUTPUT

![Screenshot (475)](https://github.com/ArpanBardhan/Login-Page-in-Android-Studio/assets/119405037/2a089686-9409-43cb-9e89-b8640218fb08)
![Screenshot (476)](https://github.com/ArpanBardhan/Login-Page-in-Android-Studio/assets/119405037/746b6fa8-36d4-4626-b449-a17c0665c2fb)







