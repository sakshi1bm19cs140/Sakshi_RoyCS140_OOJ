//Write a java program to calculate roots of quadratic equation
import java.lang.Math;
import java.util.Scanner;
class Quad {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        int a, b, c;
        double root1, root2, realPart, imgPart;
        System.out.println("Enter the value of a,b and c\n");
        a = in.nextInt();
        b = in.nextInt();
        c = in.nextInt();
        double D = (b * b) - (4 * a * c);
        if (D > 0) {
            root1 = (-b + Math.sqrt(D)) / (2 * a);
            root2 = (-b - Math.sqrt(D)) / (2 * a);
            System.out.println("The roots of the quadratic equation are:" + root1 + " " + root2);
        } else if (D == 0) {
            root1 = root2 = b / (2 * a);
            System.out.println("The roots of the quadratic equation are:" + root1 + " " + root2);
        } else {
            realPart = -b / (2 * a);
            imgPart = Math.sqrt(-D) / (2 * a);
            root1 = realPart + imgPart;
            root2 = realPart - imgPart;
            System.out.println("The roots of the quadratic equation are:" + root1 + " " + root2);
        }
    }
}

/*Develop a Java program to create a class Student with members usn, name, an array
credits and an array marks. Include methods to accept and display details and a method to
calculate SGPA of a student.
*/
import java.util.Scanner;
class Student
{
	private String USN;
	private String name;
	private int n;
	private double SGPA = 0;
	private int totalCredits = 0;
  private int credits[];
  private double marks[];
	Scanner ss = new Scanner(System.in);

	void Details()
	{
	System.out.println("Enter USN of the student");
	USN = ss.nextLine();
	System.out.println("Enter Name of the student");
	name = ss.nextLine();
	System.out.println("Enter no of subjects");
	n = ss.nextInt();
	credits = new int[n];
	marks = new double[n];
	System.out.println("*Enter details of the subjects:*");
	for(int i=0;i<n;i++)
	{
		System.out.println("Enter credits allotted to the subject "+(i+1));
		credits[i] = ss.nextInt();
		System.out.println("Enter marks in the subject "+(i+1));
		marks[i] = ss.nextInt();
		Calculate(credits[i],marks[i],i);
	}
    }
    void Calculate(int credit,double mark,int j)
    {
		totalCredits = totalCredits + credit;
		if(mark>=90&&mark<=100)
			SGPA = SGPA + (10*credit);
		else if(mark>=80 && mark<=89)
			SGPA = SGPA + (9*credit);
		else if(mark>=70&&mark<=79)
			SGPA = SGPA + (8*credit);
		else if(mark>=60&&mark<=69)
			SGPA = SGPA + (7*credit);
		else if(mark>=50 && mark<=59)
			SGPA = SGPA + (6*credit);
		else if(mark>=40&&mark<=49)
			SGPA = SGPA + (5*credit);
		else
			System.out.println("Failed in Subject "+(j+1));
	}
	void Display()
	{
		System.out.println("Details of the Student");
    System.out.println("USN: "+USN);
    System.out.println("Name :"+name);
		System.out.println("SGPA of Student "+(SGPA/totalCredits));
	}
}
class Main
{
	public static void main(String args[])
	{
		Student s1 = new Student();
		s1.Details();
		s1.Display();
	}
}

