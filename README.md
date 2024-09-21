# CodeAlpha_Java_Prpgramming_Task2
// Task 2:Online Quiz Platform

// A Simple Banking Application in Java is an ideal project
// for coding beginners. It covers fundamental concepts
// like the Scanner class for input, strings, loops, methods,
// and conditional statements. This project involves basic
// banking operations such as deposits, withdrawals,
// checking balances, and exiting the program.

import java.util.Scanner;

class BankAccount {
    private double balance;

    public BankAccount() {
        this.balance = 0.0;
    }

    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
            System.out.println("Successfully deposited: Rs " + amount);
        } else {
            System.out.println("Deposit amount must be positive.");
        }
    }

    public void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
            System.out.println("Successfully withdrew: Rs " + amount);
        } else if (amount > balance) {
            System.out.println("Insufficient balance.");
        } else {
            System.out.println("Withdrawal amount must be positive.");
        }
    }

    public double getBalance() {
        return balance;
    }
}

public class SimpleBankingApplication {
    private static Scanner scanner = new Scanner(System.in);
    private static BankAccount account = new BankAccount();

    public static void main(String[] args) {
        System.out.println("Welcome to the Simple Banking Application!");

        while (true) {
            System.out.println("\n1. Deposit");
            System.out.println("2. Withdraw");
            System.out.println("3. Check Balance");
            System.out.println("4. Exit");
            System.out.print("Choose an option: ");

            int choice = scanner.nextInt();
            switch (choice) {
                case 1:
                    deposit();
                    break;
                case 2:
                    withdraw();
                    break;
                case 3:
                    checkBalance();
                    break;
                case 4:
                    System.out.println("Exiting the application. Thank you!");
                    return;
                default:
                    System.out.println("Invalid choice. Please try again.");
            }
        }
    }

    private static void deposit() {
        System.out.print("Enter deposit amount: Rs ");
        double amount = scanner.nextDouble();
        account.deposit(amount);
    }

    private static void withdraw() {
        System.out.print("Enter withdrawal amount: Rs ");
        double amount = scanner.nextDouble();
        account.withdraw(amount);
    }

    private static void checkBalance() {
        System.out.printf("Current balance: $%.2f%n", account.getBalance());
    }
}

