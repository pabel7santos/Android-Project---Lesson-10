# Android-Project---Lesson-10
Android Project - Lesson 10

//************START HERE WITH THE TEXT - DESIGN *************//
// USING VIEWGROUP - LinearLayout

ACTIVITY_MAIN.XML
<?xml version="1.0" encoding="utf-8"?>

<LinearLayout

    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:paddingBottom="16dp"
    android:paddingLeft="16dp"
    android:paddingRight="16dp"
    android:paddingTop="16dp" >

    <TextView
        android:id="@+id/qua_text_view"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="quantity"
        android:textAllCaps="true" />

    <Button
        android:id="@+id/_text_view"
        android:layout_width="48dp"
        android:layout_height="48dp"
        android:text="+"
        android:textSize="16sp"
        android:layout_marginTop="16dp"
        android:onClick="increment" />

    <TextView
        android:id="@+id/quantity_text_view"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textSize="16sp"
        android:textColor="@android:color/black"
        android:text="0"
        android:layout_marginLeft="20dp"
        android:layout_marginTop="0dp"/>

    <Button
        android:layout_width="48dp"
        android:layout_height="48dp"
        android:onClick="decrement"
        android:layout_marginTop="0dp"
        android:text="-" />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textSize="16sp"
        android:layout_marginTop="16dp"
        android:textAllCaps="true"
        android:text="price" />

    <TextView
        android:id="@+id/price_text_view"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textSize="16sp"
        android:layout_marginTop="16dp"
        android:textColor="@android:color/black"
        android:text="$0" />

    <Button
        android:id="@+id/order_text_view"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        android:onClick="submitOrder"
        android:text="order" />

</LinearLayout>


//***********************  MainActivity.java  ***********************//


import android.os.Bundle;
import android.support.v7.app.AppCompatActivity;
import android.view.View;
import android.widget.TextView;
import java.text.NumberFormat;

public class MainActivity extends AppCompatActivity
{
    int quantity = 0;

    @Override
    protected void onCreate(Bundle savedInstanceState)
    {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }
    /*** This method is called increment when click button.  */
    public void increment(View view)
    {
       quantity = quantity + 1;
              display(quantity);
    }
    /*** This method is called decrement when click button. */
    public void decrement(View view)
    {
        quantity = quantity - 1;
               display(quantity);
    }
    /*** This method is called when the order button is clicked. */
    public void submitOrder(View view)    {
            displayPrice(quantity * 5);
    }
    /*** This method displays the given quantity value on the screen. */
    private void display(int number)
    {
        TextView quantityTextView = (TextView) findViewById
                (
                R.id.quantity_text_view);
        quantityTextView.setText("" + number);
    }
    /*** This method displays the given price on the screen. */
    private void displayPrice(int number)
    {
        TextView priceTextView = (TextView) findViewById(R.id.price_text_view);
        priceTextView.setText(NumberFormat.getCurrencyInstance().format(number));
    }
}



**************** END - TEST USING AN EMULATOR ***********

