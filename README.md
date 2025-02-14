[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/kEz0V4IK)
import java.util.Scanner;

public class ATMWithdrawalSystem {

    public static void main(String[] args) {
        // Initial balance
        double balance = 5000.00; // Initial balance in the ATM account
        Scanner scanner = new Scanner(System.in);

        // ATM System Menu
        System.out.println("Welcome to the ATM System");
        System.out.println("Select an option:");
        System.out.println("1. Check Balance");
        System.out.println("2. Withdraw Money");
        System.out.println("3. Exit");

        while (true) {
            System.out.print("Enter your choice: ");
            int choice = scanner.nextInt();

            switch (choice) {
                case 1: // Check balance
                    System.out.println("Your current balance is: $" + balance);
                    break;

                case 2: // Withdraw money
                    System.out.print("Enter the amount to withdraw: $");
                    double withdrawAmount = scanner.nextDouble();

                    if (withdrawAmount <= 0) {
                        System.out.println("Invalid amount. Please enter a positive value.");
                    } else if (withdrawAmount > balance) {
                        System.out.println("Insufficient balance! Your current balance is: $" + balance);
                    } else {
                        balance -= withdrawAmount;
                        System.out.println("You have successfully withdrawn: $" + withdrawAmount);
                        System.out.println("Your remaining balance is: $" + balance);
                    }
                    break;

                case 3: // Exit
                    System.out.println("Thank you for using the ATM. Goodbye!");
                    scanner.close();
                    System.exit(0);
                    break;

                default:
                    System.out.println("Invalid choice! Please enter a valid option.");
                    break;
            }

            System.out.println("\nSelect another option:");
            System.out.println("1. Check Balance");
            System.out.println("2. Withdraw Money");
            System.out.println("3. Exit");
        }
    }
}
