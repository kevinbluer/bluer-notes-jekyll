---
layout: page
title: Java
permalink: /java/
---

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

##### Day 3

{% highlight java %}
import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;
public class Solution {
   
   public static void main(String[] args) {
      Scanner scan = new Scanner(System.in);
      int n = scan.nextInt(); 
      scan.close();
      String ans="";
          
      // if 'n' is NOT evenly divisible by 2 (i.e.: n is odd)
      if ((n%2==1) || (n%2==0 && (n >= 6 && n <= 20))){
         ans = "Weird";
      }
      else if ((n%2==0 && (n >= 2 && n <= 5)) || (n%2==0 && (n > 20 ))) {
         ans = "Not Weird";
      }
      System.out.println(ans);
   }
}
{% endhighlight %}


##### Day 4

{% highlight java %}
public class Person {
    private int age;	
  
	public Person(int initialAge) {
  		// Add some more code to run some checks on initialAge
        if (initialAge < 0) {
            System.out.println("Age is not valid, setting age to 0.");
            this.age = 0;
        } else {
            this.age = initialAge;
        }
	}

	public void amIOld() {
  		// Write code determining if this person's age is old and print the correct statement:
        
        if (this.age < 13) {
            System.out.println("You are young.");    
        } else if (this.age >= 13 && this.age < 18) {
            System.out.println("You are a teenager.");
        } else {
            System.out.println("You are old.");
        }
	}

	public void yearPasses() {
  		// Increment this person's age.
        this.age++;
	}
}
{% endhighlight %}