# Simple SnackBar
Membuat Simple SnackBar di Android Studio<br />

Buat Project Baru dengan Nama SimpleSnackbar
```
File > New > New Project
```
Tambahkan dependesi di <b>build.gradle (Module: app)</b><br />
<img src="https://github.com/moeslimdecoded/simple-snackbar/blob/master/setgradle.png"><br>
Gambar 1.1 - Menampilkan dan menambahkan File Dependensi ke build.gradle</b><br />

Kemudian jika project sudah tampil pada <b>activity_main.xml</b> buat tampilan nya seperti dibawah ini:
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:padding="20dp"
    android:orientation="vertical"
    android:id="@+id/linearLayouts"
    tools:context="id.co.dev.moeslim.textview.homeActivity">

    <LinearLayout
        android:layout_width="fill_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        android:paddingLeft="20dp"
        android:paddingRight="20dp"
        app:layout_behavior="@string/appbar_scrolling_view_behavior">

        <Button
            android:id="@+id/btnSimpleSnackbar"
            android:layout_width="fill_parent"
            android:layout_height="wrap_content"
            android:layout_marginTop="30dp"
            android:text="Simple Snackbar" />

        <Button
            android:id="@+id/btnActionCallback"
            android:layout_width="fill_parent"
            android:layout_height="wrap_content"
            android:layout_marginTop="10dp"
            android:text="With Action Callback" />

        <Button
            android:id="@+id/btnCustomSnackbar"
            android:layout_width="fill_parent"
            android:layout_height="wrap_content"
            android:layout_marginTop="10dp"
            android:text="Custom Color" />

    </LinearLayout>

</LinearLayout>
```
Berikut tampilannya:<br />
<img src="https://github.com/moeslimdecoded/simple-snackbar/blob/master/views.png" ><br />
Gambar 1.2 - Tampilan Setelah Di Design Melalui file <b>activity_main.xml</b><br />

Berikutnya masuk ke bagian <b>mainActivity.java</b><br />
```
package id.co.dev.moeslim.textview;

import android.graphics.Color;
import android.support.design.widget.Snackbar;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.LinearLayout;
import android.widget.TextView;

public class homeActivity extends AppCompatActivity {

    //Deklarasikan Layout
    LinearLayout linearLayout
    //Deklarasikan button
    Button btnSimpleSnackbar, btnActionCallback, btnCustomView;
    
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_home);
        
        //Instansiasikan
        linearLayout = (LinearLayout)findViewById(R.id.linearLayouts);
        btnSimpleSnackbar = (Button)findViewById(R.id.btnSimpleSnackbar);
        btnActionCallback = (Button)findViewById(R.id.btnActionCallback);
        btnCustomView = (Button)findViewById(R.id.btnCustomSnackbar);

        //Action's
        btnSimpleSnackbar.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                //Create Simple Snackbar
                Snackbar snackbar = Snackbar.make(linearLayout, "Welcome, SMK Rabbaanii", Snackbar.LENGTH_LONG);
                snackbar.show();
            }
        });

        btnActionCallback.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                //Create SnackBar with rollback
                Snackbar snackbar = Snackbar
                        .make(linearLayout, "Message is deleted!!", Snackbar.LENGTH_LONG)
                        .setAction("Undo", new View.OnClickListener() {
                            @Override
                            public void onClick(View view) {
                                Snackbar snackbar1 = Snackbar.make(linearLayout, "Message is restored!!", Snackbar.LENGTH_SHORT);
                                snackbar1.show();
                            }
                        });
                snackbar.show();
            }
        });

        btnCustomView.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                //Create SnackBar with Custom Snackbar
                Snackbar snackbar = Snackbar
                        .make(linearLayout, "No internet connection!", Snackbar.LENGTH_LONG)
                        .setAction("Retry", new View.OnClickListener() {
                            @Override
                            public void onClick(View view) {

                            }
                        });

                // Changing message text color
                snackbar.setActionTextColor(Color.RED);

                // Changing action button text color
                View sbView = snackbar.getView();
                TextView textView = (TextView)sbView.findViewById(android.support.design.R.id.snackbar_text);
                textView.setTextColor(Color.YELLOW);

                snackbar.show();
            }
        });
    }
}
```
Berikut :<br />
