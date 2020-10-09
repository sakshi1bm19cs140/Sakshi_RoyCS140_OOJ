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

/*
  Develop a Java program to create a class Book with members – bookid, booktitle,
  no_of_pages, year_of_pub, author, publisher and price. Create three objects of book
  class. Include methods in Book class that do the following:
  a. Accepting the book details
  b. Displaying the book details
  c. Accept the author name and display the book details.
  d. Display the booktitle of the most expensive book
  e. Display the count of the books published in the year 2020.
  f. Display the book details of the book with the least number of pages.
  */
  
  import java.util.Scanner;
  class Book
  {
      private int id;
      private String title;
      private int nop;
      private int year;
      private String auth;
      private String pub;
      private double p;
      void getdetails()
      {
          Scanner s=new Scanner(System.in);
          System.out.println("ENTER ID OF BOOK");
          id=s.nextInt();
          System.out.println("ENTER THE TITLE OF BOOK");
          title=s.next();
          System.out.println("ENTER NUMBER OF PAGES OF BOOK");
          nop=s.nextInt();
          System.out.println("ENTER YEAR OF PUBLISHING OF THE BOOK");
          year=s.nextInt();
          System.out.println("ENTER AUTHOR OF BOOK");
          auth=s.next();
          System.out.println("ENTER PUBLISHER OF BOOK");
          pub=s.next();
          System.out.println("ENTER PRICE OF BOOK");
          p=s.nextDouble();
      }
      void printdetails()
      {
          System.out.println("  ID OF BOOK: "+id);
          System.out.println("  TITLE OF BOOK: "+title);
          System.out.println("  NUMBER OF PAGES OF BOOK: "+nop);
          System.out.println("  YEAR OF PUBLISHING OF THE BOOK: "+year);
          System.out.println("  AUTHOR OF BOOK: "+auth);
          System.out.println("  PUBLISHER OF BOOK: "+pub);
          System.out.println("  PRICE OF BOOK: "+p);
      }
      double price()
      {
          return p;
      }
      void displaybooktitle()
      {
          System.out.println(title);
      }
      int year()
      {
          return year;
      }
      int pages()
      {
          return nop;
      }
      String author()
  {
     return auth;
  }
  }
  class BookMain
  {
      public static void main(String args[])
      {
          int c=0;
          Book b1=new Book();
          Book b2=new Book();
          Book b3=new Book();
          b1.getdetails();
          b2.getdetails();
          b3.getdetails();
          System.out.println("**DETAILS OF THE BOOK1**");
          b1.printdetails();
          System.out.println("\n**DETAILS OF THE BOOK2**");
          b2.printdetails();
          System.out.println("\n**DETAILS OF THE BOOK3**");
          b3.printdetails();
          if(b1.price()>=b2.price() && b1.price()>=b3.price())
          {
          System.out.println("\nTHE MOST EXPENSIVE BOOK IS WITH TITLE:  ");
          b1.displaybooktitle();
          }
          else if(b2.price()>=b1.price() && b2.price()>=b3.price())
          {
          System.out.println("THE MOST EXPENSIVE BOOK IS WITH TITLE:  ");
          b2.displaybooktitle();
          }
          else
          {
          System.out.println("THE MOST EXPENSIVE BOOK IS WITH TITLE:  ");
          b3.displaybooktitle();
          }
          if(b1.year()==2020)
          c++;
          if(b2.year()==2020)
          c++;
          if(b3.year()==2020)
          c++;
          System.out.println("THE NUMBER OF BOOKS PUBLISHED IN THE YEAR 2020 = "+c);
          if(b1.pages()<=b2.price() && b1.price()<=b3.price())
         {
          System.out.println("THE  BOOK  WITH LEAST NUMBER OF PAGES IS BOOK 1 ");
          b1.printdetails();
          }
          else if(b2.pages()<=b1.pages() && b2.pages()<=b3.pages())
          {
          System.out.println("THE  BOOK  WITH LEAST NUMBER OF PAGES IS BOOK 2 ");
          b2.printdetails();
          }
          else
          {
              System.out.println("THE  BOOK  WITH LEAST NUMBER OF PAGES IS BOOK 3 ");
              b3.printdetails();
          }
      System.out.println("ENTER THE AUTHOR NAME WHOSE BOOK DETAILS NEED TO BE DISPLAYED");
      Scanner s1=new Scanner(System.in);
      String auth1=s1.next();
      if(auth1.compareToIgnoreCase(b1.author())==0)
      b1.printdetails();
     else if(auth1.compareToIgnoreCase(b2.author())==0)
      b2.printdetails();
     else if(auth1.compareToIgnoreCase(b3.author())==0)
      b3.printdetails();
      else
        System.out.println("THE GIVEN AUTHOR'S BOOK IS NOT FOUND");
  }
  }

