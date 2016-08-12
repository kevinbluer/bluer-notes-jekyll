---
layout: page
title: Java
permalink: /java/
---

# Java

### 30 days of code challenges

###### Day 0

{% highlight java %}
public class Solution {
	public static void main(String[] args) {
        // Create a Scanner object to read input from stdin.
		Scanner scan = new Scanner(System.in); 
		
		// Read a full line of input from stdin and save it to our variable, inputString.
		String inputString = scan.nextLine(); 

		// Close the scanner object, because we've finished reading 
        // all of the input from stdin needed for this challenge.
		scan.close(); 
      
		// Print a string literal saying "Hello, World." to stdout.
		System.out.println("Hello, World.");
      
	    // TODO: Write a line of code here that prints the contents of inputString to stdout.
	}
}
{% endhighlight %}

###### Day 1

{% highlight java %}
/* Declare second integer, double, and String variables. */
int i2;
double d2;
String s2;

/* Read and save an integer, double, and String to your variables.*/
i2 = scan.nextInt();
scan.nextLine();
d2 = scan.nextDouble();
scan.nextLine();
s2 = scan.nextLine();
    
/* Print the sum of both integer variables on a new line. */
System.out.println(i + i2);

/* Print the sum of the double variables on a new line. */
System.out.println(d + d2);

/* Concatenate and print the String variables on a new line; 
	the 's' variable above should be printed first. */
System.out.println(s + s2);
{% endhighlight %}

###### Day 2

{% highlight java %}
import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;
public class Arithmetic {

    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        double mealCost = scan.nextDouble(); // original meal price
        int tipPercent = scan.nextInt(); // tip percentage
        int taxPercent = scan.nextInt(); // tax percentage
        scan.close();
        
        // Write your calculation code here.
        double preTotalCost;
        
        preTotalCost = mealCost + (mealCost*(tipPercent/100.0f)) + (mealCost*(taxPercent/100.0f));
      
        // cast the result of the rounding operation to an int and save it as totalCost 
        int totalCost = (int) Math.round(preTotalCost);
      
        // Print your result
        System.out.println("The total meal cost is " + totalCost + " dollars.");
    }
}
{% endhighlight %}