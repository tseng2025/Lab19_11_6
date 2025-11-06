# Lab19_11_6
This program asks users to input grades and save them in grades.txt then uses try-catch to catch the exceptions. This prints out student names and grades.
## How to Run
1. Open the program in your IDE.
2. Enter students' scores.
***   
Example output
Enter John's grade: 85
Enter Sara's grade: 65
Enter Mark's grade: 95

Student Grades: 
John: 85
Sara: 65
Mark: 95
---
My Code

import java.io.FileWriter;
import java.io.IOException;
import java.util.InputMismatchException;
import java.util.Scanner;
import java.io.File;
import java.io.FileNotFoundException;

public class Main{
    public static void main(String[]args) throws IOException{
        Scanner input = new Scanner(System.in);
        FileWriter grade=new FileWriter("grades.txt");
        try{
            System.out.print("Enter John's grade: ");
            int grade1 = input.nextInt();
            grade.write("John: "+grade1+"\n");

            System.out.print("Enter Sara's grade: ");
            int grade2 = input.nextInt();
            grade.write("Sara: "+grade2+"\n");

            System.out.print("Enter Mark's grade: ");
            int grade3 = input.nextInt();
            grade.write("Mark: "+grade3+"\n");
        }
        catch(Exception e){
            System.out.println("Invalid input. ");
        }
        grade.close();

        System.out.println();

        try {
            File myFile = new File("grades.txt");
            Scanner ip = new Scanner(myFile);
            System.out.println("Student Grades: ");
            while (ip.hasNextLine()) {
                System.out.println(ip.nextLine());
            }
            ip.close();
        }
        catch(Exception e){
            System.out.print("File not found!");
        }
    }
}
***
Author
Hsiayen Tseng
