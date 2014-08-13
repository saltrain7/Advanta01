---
layout: code
title: 16x2 LCD
permalink: /16x2LCD.htm
---

# 16x2 LCD
Learn how to use the 16x2 LCD shield with the Arduino Liquid Crystal Library.

# Required Components
* <a href="https://www.sparkfun.com/products/255" target="_blank">16x2 LCD</a>

# Hooking up Components
If you are using the 16x2 LCD listed above, follow the diagram below:<br/>
<img src="images/16x2LCDDiagram.png">

# Create a new project

1. Create a new project from the template.
1. Go to <a href="https://github.com/arduino/Arduino/tree/master/libraries/LiquidCrystal" target="_blank">Arduino's Liquid Crystal Library GitHub</a> and download the LiquidCrystal.cpp and LiquidCrystal.h files.
1. Place the LiquidCrystal.cpp and LiquidCrystal.h files in your new project.
1. Based on your 16x2 LCD you may need to specify other pins for use with the LiquidCrystal library.
1. Replace the existing code in main.cpp with the following code:

# Code

{% highlight C++ %}
// Main.cpp : Defines the entry point for the console application.
//

#include "stdio.h"
#include "tchar.h"
#include "arduino.h"
#include "LiquidCrystal.h" // we need this library for the LCD commands

LiquidCrystal *lcd; // define our LCD and which pins to use
int RS = 4;
int ENABLE = 5;
int D0 = 6;
int D1 = 7;
int D2 = 8;
int D3 = 9;

int _tmain(int argc, _TCHAR* argv [])
{
    return RunArduinoSketch();
}

void setup()
{
    Log(L"LCD Sample\n");

    lcd = new LiquidCrystal(RS, ENABLE, D0, D1, D2, D3);
    lcd->begin(16, 2); // need to specify how many columns and rows are in the LCD unit
    lcd->clear();      // this clears the LCD. You can use this at any time

    lcd->setCursor(0, 0);
    lcd->print("Hello!");
}

void loop()
{
}
{% endhighlight %}
  <hr/>

<a class="btn btn-default" href="SampleApps.htm" role="button">&laquo; Return to Samples</a>
