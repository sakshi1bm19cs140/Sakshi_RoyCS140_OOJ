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
