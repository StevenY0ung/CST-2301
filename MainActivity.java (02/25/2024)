package com.example.programminglanguage;

import androidx.appcompat.app.AlertDialog;
import androidx.appcompat.app.AppCompatActivity;

import android.content.DialogInterface;
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.AdapterView;
import android.widget.ArrayAdapter;
import android.widget.ListView;
import android.widget.TextView;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {

    ListView progLangLV;
    TextView outputTV;
    String progLangArray[] = {"1. Python", "2. C" , "3. C++" , "4. Java" , "5. C#" , "6. Javascript" , "7. SQL" , "8. GO" , "9. Visual Basic" , "10. PHP"};
    String progLangpctgArray[] = {"15.16%" , "10.97%" , "10.53%" , "8.88%" , "7.53%" , "3.17%" , "1.82%" , "1.73%" , "1.52%" , "1.51%"};

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Define ListView object
        progLangLV = findViewById(R.id.proglanglvID);
        outputTV = findViewById(R.id.outputtvID);

        // Create ArrayAdapter
        ArrayAdapter<String> proglangAA = new ArrayAdapter<>(MainActivity.this, android.R.layout.simple_list_item_1, progLangArray);

        // Set the adapter
        progLangLV.setAdapter(proglangAA);

        progLangLV.setOnItemClickListener(new AdapterView.OnItemClickListener() {
            @Override
            public void onItemClick(AdapterView<?> parent, View view, int i, long id) {
                // Show a toast with the selected programming language and its percentage
                Toast.makeText(MainActivity.this, progLangArray[i] + "(" + progLangpctgArray[i] + ")", Toast.LENGTH_LONG).show();

                // Update the outputTV with the selected programming language and its percentage
                outputTV.setText(progLangArray[i] + "(" + progLangpctgArray[i] + ")");

                String selectedLanguage = progLangArray[i];

                String languagePercentage = progLangpctgArray[i];

                displayAlertDialog(selectedLanguage, languagePercentage);

                Intent gotoScreen2= new Intent(MainActivity.this, Screen2.class);

                gotoScreen2.putExtra("percentageKey" , languagePercentage);

                startActivity(gotoScreen2);

                // Call the displayAlertDialog method
                displayAlertDialog(progLangArray[i], progLangpctgArray[i]);
            }
        });
    }

    // Define the displayAlertDialog method
    public void displayAlertDialog(String lang, String pctg) {
        // Your code for displaying an alert dialog
        AlertDialog.Builder alertDialog = new AlertDialog.Builder(MainActivity.this);

        alertDialog.setTitle("Top 10 Programming Language");
        alertDialog.setMessage(lang + "(" + pctg + ")");

        alertDialog.setPositiveButton("Exit", new DialogInterface.OnClickListener() {
            @Override
            public void onClick(DialogInterface dialogInterface, int i) {
                restart();
            }
        });

        alertDialog.create();

        alertDialog.show();
    }

    private void restart() {
        Intent intent = new Intent(this, MainActivity.class);
        startActivity(intent);
        finishAffinity();
    }
}
