# HelloWorld
This is the pre work Hello world project for android assignment
I LOVE TO CODE!
package com.example.user.helloworld;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.text.TextUtils;
import android.util.Log;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        //this is to make the change text color button clickable:
        findViewById(R.id.button).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                ((TextView) findViewById(R.id.TextView)).setTextColor(
                        getResources().getColor(R.color.colorAccent));
            }
        });

        //this is to make the background button clickable:
        findViewById(R.id.button3).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                findViewById(R.id.wonderful).setBackgroundColor(
                        getResources().getColor(R.color.tealish));
            }
        });

        //this is to make the change text button clickable
        findViewById(R.id.button4).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                /*grabbing the user input
                putting the text when button of change text is clicked*/
                String newText = ((EditText)findViewById(R.id.editText)).getText().toString();

                if(TextUtils.isEmpty(newText)){
                    ((TextView) findViewById(R.id.TextView)).setText("Hello from Christian!");
                }
                else{
                    ((TextView) findViewById(R.id.TextView)).setText(newText);
                }
            }
        });

        //this button to reset the color back to original everything
        findViewById(R.id.wonderful).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                //resetting the text back to original.
                ((TextView) findViewById(R.id.TextView)).setTextColor(
                        getResources().getColor(R.color.orange));

                //resetting the background color
                findViewById(R.id.wonderful).setBackgroundColor(
                        getResources().getColor(R.color.colorPrimary));

                //resetting the text back to Hello
                        ((TextView) findViewById(R.id.TextView)).setText("Hello from Christian!");
                    }
                });
        }
    }
