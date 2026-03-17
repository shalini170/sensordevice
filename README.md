# Ex.No:4 Develop a simple application to display the avaliable sensor in android mobile devices using Sensor Manager in android studio.


## AIM:

To develop a sensor application to use the sensor manager class to identify and get the list of available sensors on a device. in Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Min.required Giraffe)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as Sensor and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Display avaliable sensor in android mobile devices.

Step 7: Save and run the application.

## PROGRAM:
```
/*
Program to print the avaliable sensor in android mobile devices”.
Developed by: shalini venkatesulu
Registeration Number : 212223220104
*/
```
## MainActivity.java
```java
package com.example.sensorlistapp;

import androidx.appcompat.app.AppCompatActivity;
import android.content.Context;
import android.hardware.Sensor;
import android.hardware.SensorManager;
import android.os.Bundle;
import android.widget.TextView;
import java.util.List;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Get TextView references
        TextView tvCount = findViewById(R.id.tvCount);
        TextView tvSensors = findViewById(R.id.tvSensors);

        // Get SensorManager
        SensorManager sensorManager = (SensorManager) getSystemService(Context.SENSOR_SERVICE);
        
        // Get all sensors
        List<Sensor> sensors = sensorManager.getSensorList(Sensor.TYPE_ALL);
        
        // Update count
        tvCount.setText("Total Sensors: " + sensors.size());
        
        // Build sensor list
        StringBuilder sensorList = new StringBuilder();
        
        for (Sensor sensor : sensors) {
            sensorList.append("• ").append(sensor.getName()).append("\n");
        }
        
        // Display list
        if (sensors.size() > 0) {
            tvSensors.setText(sensorList.toString());
        } else {
            tvSensors.setText("No sensors found!");
        }
    }
}
```
## activity_main.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp">

    <TextView
        android:id="@+id/tvTitle"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Available Sensors"
        android:textSize="22sp"
        android:textStyle="bold"
        android:gravity="center"
        android:layout_marginBottom="10dp"/>

    <TextView
        android:id="@+id/tvCount"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Count: 0"
        android:textSize="16sp"
        android:layout_marginBottom="10dp"/>

    <ScrollView
        android:layout_width="match_parent"
        android:layout_height="match_parent">

        <TextView
            android:id="@+id/tvSensors"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Loading..."
            android:textSize="14sp"/>

    </ScrollView>

</LinearLayout>
```
## OUTPUT
![Screenshot_20260209_161241_SensorListApp](https://github.com/user-attachments/assets/13460e14-fb88-4118-ad6a-61fd546049bb)




## RESULT
Thus a Simple Android Application to display the avaliable sensor in android mobile devices using Sensor Manager in Android Studio is developed and executed successfully.
