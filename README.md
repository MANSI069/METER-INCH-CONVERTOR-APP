# METER-INCH-CONVERTOR-APP
Developed a meter inch convertor app 


package com.example.metertoinches;

import androidx.appcompat.app.AppCompatActivity;

import android.graphics.Color;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {

    private EditText EnterInMeters;
    private Button Covertbutton;
    private TextView Resultid;
    private EditText EnterInInches;
    private Button CovertButton2;
    private TextView ResultId2;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        EnterInMeters=(EditText) findViewById(R.id.EnterInMeters);
        Resultid=(TextView) findViewById(R.id.Resultid);
        Covertbutton=(Button) findViewById(R.id.Convertbutton);
        Covertbutton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                double permeteravalue=39.37;
                double result=0.0;

                if(EnterInMeters.getText().toString().equals(""))
                {
                    Resultid.setText(R.string.Error_Message);
                    Resultid.setTextColor(Color.RED);
                }
                else
                {
                    double getEditText=Double.parseDouble(EnterInMeters.getText().toString());
                    result=getEditText*permeteravalue;

                    Resultid.setTextColor(Color.DKGRAY);
                    Resultid.setText(String.format("%.2f",result)+" Inches");
                }

            }
        });

        EnterInInches=(EditText) findViewById(R.id.EnterInInches);
        ResultId2=(TextView) findViewById(R.id.ResultId2);
        CovertButton2=(Button) findViewById(R.id.ConvertButton2);
        CovertButton2.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                double perinchavalue=0.0254;
                double result1=0.0;

                if(EnterInInches.getText().toString().equals(""))
                {

                    ResultId2.setText(R.string.Error_Message);
                    ResultId2.setTextColor(Color.RED);

                }
                else {
                    double getEditText1 = Double.parseDouble(EnterInInches.getText().toString());
                    result1 = getEditText1 * perinchavalue;

                    ResultId2.setTextColor(Color.DKGRAY);
                    ResultId2.setText(String.format("%.2f", result1) + " Meters");
                }
            }
        });


    }
}
