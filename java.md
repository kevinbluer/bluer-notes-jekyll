---
layout: page
title: Java
permalink: /java/
---

### 30 days of code challenges

#### Day 0

{% highlight java %}
public class Solution {
	public static void main(String[] args) {
		Scanner scan = new Scanner(System.in); 		
		String inputString = scan.nextLine(); 
		scan.close(); 
		System.out.println("Hello, World.");
	}
}
{% endhighlight %}

#### Day 1

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

#### Day 2

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

#### Day 3

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


#### Day 4

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

#### Day 5

{% highlight java %}
import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;

public class Solution {

    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        int N = in.nextInt();
        
        int i;
        for (i = 1; i <= 10; i++) {
            System.out.println(N + " x " + i + " = " + (i * N));
        }
    }
}
{% endhighlight %}

#### Day 6

{% highlight java %}
import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;

public class Solution {

    public static void main(String[] args) {
        
      Scanner scan = new Scanner(System.in);
      int T = scan.nextInt();
      
      // jump to the next line
      scan.nextLine();
        
      int i;
      for (i = 1; i <= T; i++) {
          
        String str = scan.nextLine();
        char[] charArray = str.toCharArray();
          
        String x = "";
        String y = "";
          
        int z;
        for (z = 0; z < charArray.length; z++) {
            
            if (z%2==0) {
                x += charArray[z];
            } else {
                y += charArray[z];
            }
        }
        
        System.out.println(x + " " + y);
      }
        
      scan.close();
    }
}
{% endhighlight %}

#### Day 7

{% highlight java %}
import java.io.*;
import java.util.*;


public class Solution {

    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        int n = in.nextInt();
        int[] arr = new int[n];
        for(int i=0; i < n; i++){
            arr[i] = in.nextInt();
        }
        
        String out = "";
        for (int x=arr.length; x > 0; x--) {
            out = out + arr[x-1] + " ";
        }
        
        System.out.println(out);
        
        in.close();
    }
}
{% endhighlight %}

#### Day 8

{% highlight java %}
//Complete this code or write your own from scratch
import java.util.*;
import java.io.*;

class Solution{
    public static void main(String []argh){
        Scanner in = new Scanner(System.in);
        int n = in.nextInt();
        
        Map<String, Integer> dictionary = new HashMap<String, Integer>();
        
        for(int i = 0; i < n; i++){
            String name = in.next();
            int phone = in.nextInt();
            dictionary.put(name, phone);
        }
        while(in.hasNext()){
            String s = in.next();
            if (dictionary.get(s) != null) {
                System.out.println(s + "=" + dictionary.get(s));
            } else {
                System.out.println("Not found");
            }
            
        }
        in.close();
    }
}
{% endhighlight %}

#### Day 9

{% highlight java %}
import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;

public class Solution {
    public static int total;
    
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        int n = scan.nextInt();
        
        total = n;
        factorial(n);
    }
    
    public static void factorial(int n) {
        if (n <= 1) {
            System.out.println(total);
        } else {
            total = total * (n-1);
            factorial(n-1);
        }
    }
}
{% endhighlight %}

#### Day 10

{% highlight java %}
import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;

public class Solution {

    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        int n = in.nextInt();
        
        char[] base2 = Integer.toString(n, 2).toCharArray();
        
        int result = 0;
        int currentHighest = 0;
        
        for(int i = 0; i < base2.length; i++){
            if (base2[i] == '1') {
                result++;
                if (result >= currentHighest) {
                    currentHighest = result;
                }
            } else 
                if (Arrays.asList(base2).indexOf('1') > 0) {
                    result = 1;
                } else {
                    result = 0;
                }
            }
        }
        
        System.out.println(currentHighest);
    }
}
{% endhighlight %}