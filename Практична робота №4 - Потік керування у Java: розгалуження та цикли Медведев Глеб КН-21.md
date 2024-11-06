import java.util.Scanner;

public class PiecewiseFunction {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Input for parameters a, b, and x
        System.out.print("Enter value for a: ");
        double a = scanner.nextDouble();

        System.out.print("Enter value for b: ");
        double b = scanner.nextDouble();

        System.out.print("Enter value for x: ");
        double x = scanner.nextDouble();

        double result;

        // Calculate the function based on the value of x
        if (x >= 1 && x < 3) {
            // First case: f(x) = 9 / (a * x)
            if (a * x != 0) { // Check to avoid division by zero
                result = 9 / (a * x);
                System.out.printf("f(x) = %.2f\n", result);
            } else {
                System.out.println("Undefined result (division by zero).");
            }
        } else if (x == 3) {
            // Second case: f(x) = |a * x^2 + x + b|
            result = Math.abs(a * Math.pow(x, 2) + x + b);
            System.out.printf("f(x) = %.2f\n", result);
        } else {
            // x is out of the defined range
            System.out.println("x is out of the defined range [1, 3].");
        }

        scanner.close();
    }
}
