# GPACALC
/* Author: Joshua Lucas
 * Date: 9/14/2015
 * Description: This program will determine the current GPA of the user by taking
 * their inputs and giving them an output*/

import java.util.Scanner; //Imports the Scanner for user input
import java.applet.*; //Creates a window to place the JFrame in
import javax.swing.JApplet; //Imports the Java Applet for a visual aspect
import java.awt.*; //Creates Graphical Interface
import java.text.DecimalFormat; //Formats numbers to only show until a certain decimal place
import javax.swing.*;
  
public class Project1_JoshuaLucas
{
    public static void main(String[] args)
    { 
      
     String first_name, last_name, major, course_numberone, course_numbertwo, course_numberthree, course_oneQP, course_twoQP, course_threeQP;
     String gpastring;
     float number_of_creditsone, number_of_creditstwo, number_of_creditsthree, total_numberofcredits, course_oneQPFloat, course_twoQPFloat;
     float course_threeQPFloat, total_numberofQP,  courseonetimescredits, coursetwotimescredits, coursethreetimescredits, gpa;
     
     
     Scanner scan_in = new Scanner (System.in); //Creates a new scanner
     
     DecimalFormat fmt = new DecimalFormat("0.##"); //Shows decimals to the second place
     
     System.out.println("Hello, and welcome to your very own, personal, UNG GPA Calculator!"); //Greeting
     
     System.out.print("Please enter your first name:");
     first_name=scan_in.nextLine(); // Asks user for first name
     
     System.out.print("Please enter your last name:");
     last_name=scan_in.nextLine();  // Asks user for last name
     
     System.out.print("Please list your major:");
     major=scan_in.nextLine(); // Asks user for major
     
     System.out.println(); // Line break
     
     System.out.println("We will now need some of your course information");
     
     System.out.println(); // Line break
      
     System.out.print("Please enter the course # of your first class:"); 
     course_numberone=scan_in.next(); // Asks user for course # one
     
     System.out.print("Please enter the amount of credits this class provides:");
     number_of_creditsone=scan_in.nextInt(); // Asks user for # of credits
     
     System.out.print("Please enter the course # of your second class:"); 
     course_numbertwo=scan_in.next(); // Asks user for course # two
     
     System.out.print("Please enter the amount of credits this class provides:");
     number_of_creditstwo=scan_in.nextInt(); // Asks user for # of credits
     
     System.out.print("Please enter the course # of your third class:"); 
     course_numberthree=scan_in.next(); // Asks user for course # three
     
     System.out.print("Please enter the amount of credits this class provides:");
     number_of_creditsthree=scan_in.nextInt(); // Asks user for # of credits
     
     System.out.println("Thank you, here listed below is a chart of how many quality points are recieved for the current grade you attain in each class");
     
     System.out.println(); // Line break
     
     System.out.println(" A =4.00 A-=3.67\n B+=3.33 B =3.00 B-=2.67\n C+=2.33 C =2.00 C-=1.67\n D+=1.33 D =1.00 F =0.00"); //Quality Point Chart
     
     System.out.println(); // Line break
     
     System.out.println("Now, please provide the number of quality points you recieved for each grade to the second decimal place:");
     
     System.out.println(); // Line break
     
     System.out.print("Course "+course_numberone);
     course_oneQP=scan_in.next(); //Asks the user for number of quality points for their first class
     
     System.out.print("Course "+course_numbertwo);
     course_twoQP=scan_in.next(); //Asks the user for number of quality points for their second class
     
     System.out.print("Course "+course_numberthree);
     course_threeQP=scan_in.next(); //Asks the user for number of quality points for their third class
     
     number_of_creditsone = Float.valueOf(course_oneQP); //Converts all of these string values into floats
     number_of_creditstwo = Float.valueOf(course_twoQP);
     number_of_creditsthree = Float.valueOf(course_threeQP);
     course_oneQPFloat = Float.valueOf(course_oneQP);
     course_twoQPFloat = Float.valueOf(course_twoQP);
     course_threeQPFloat = Float.valueOf(course_threeQP);
     
     courseonetimescredits = (course_oneQPFloat * number_of_creditsone); //Multiplies the two floats together
     coursetwotimescredits = (course_twoQPFloat * number_of_creditstwo);
     coursethreetimescredits = (course_threeQPFloat * number_of_creditsthree);
     
     
     total_numberofQP = courseonetimescredits+coursetwotimescredits+coursethreetimescredits; //Defines the variable for further use
     
     total_numberofcredits = number_of_creditsone+number_of_creditstwo+number_of_creditsthree; //Defines the variable for further use
     
     gpa = total_numberofQP/total_numberofcredits; //Divides total quality points by total number of credits
     
     System.out.print("Alright "+first_name+" "+last_name+", I see that you are majoring in "+major+", very cool!"); //Shows results, and what the user inputted
     
     System.out.println();
   
     System.out.print("Your current GPA is: "+ fmt.format(gpa));
     
     System.out.println();
     
     System.out.print("You recieved "+number_of_creditsone+" for your "+course_numberone+" class.");
     
     System.out.println();
     
     System.out.print("You recieved "+number_of_creditstwo+" for your "+course_numbertwo+" class.");
     
     System.out.println();
     
     System.out.print("You recieved "+number_of_creditsthree+" for your " +course_numberthree+" class.");
     
     System.out.println();
     
     //**************************************************************************************************
     //The user input is finished by this step, and I will have to create a JFrame which is done so below.
     //**************************************************************************************************
     
     JFrame frame = new JFrame("GPA Calculator"); //Creates a new frame called "GPA Calculator"
    
     frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE); //Allows you to close the JApplet 
     
     JPanel primary = new JPanel(); //Creates a new panel called "primary"
     primary.setBackground(Color.yellow); //Sets the background color to yellow
     primary.setPreferredSize(new Dimension(210, 90)); //Sets the window size to 210 width, and 90 height
     
     gpastring = String.valueOf(gpa); //Converts gpa to a string called "gpastring"
      
     JLabel label1 = new JLabel("Hello, "+first_name+ ", Your GPA is:"); //Creates two new labels to place inside of the JFrame
     JLabel label2 = new JLabel(gpastring);

     label2.setText(String.format(gpastring)); 
     
     primary.add(label1); //Adds the two labels into the frame
     primary.add(label2);
     
     frame.getContentPane().add(primary);
     frame.pack(); //Keeps the frame from closing in onto itself when launched
     frame.setVisible(true); //Shows the frame
    }
}
       
