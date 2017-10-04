# Simple SnackBar
Membuat Simple SnackBar di Android Studio<br />

Buat Project Baru dengan Nama SimpleSnackbar
```
File > New > New Project
```
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
Gambar 1.1 - Tampilan Setelah Di Design Melalui file <b>activity_main.xml</b><br />


