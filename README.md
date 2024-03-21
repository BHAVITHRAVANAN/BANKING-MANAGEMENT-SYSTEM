import java.util.Scanner;

public class BankApplication {
    private double balance;
    private Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) {
        BankApplication bankApp = new BankApplication();
        bankApp.run();
    }

    public void run() {
        while (true) {
            System.out.println("1. Deposit");
            System.out.println("2. Withdraw");
            System.out.println("3. Check Balance");
            System.out.println("4. Exit");
            System.out.print("Enter your choice: ");
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
                    System.exit(0);
                default:
                    System.out.println("Invalid choice. Please enter a number between 1 and 4.");
            }
        }
    }

    public void deposit() {
        System.out.print("Enter amount to deposit: ");
        double amount = scanner.nextDouble();
        balance += amount;
        System.out.println("Deposit successful. Current balance is " + balance);
    }

    public void withdraw() {
        System.out.print("Enter amount to withdraw: ");
        double amount = scanner.nextDouble();
        if (amount > balance) {
            System.out.println("Insufficient balance.");
        } else {
            balance -= amount;
            System.out.println("Withdrawal successful. Current balance is " + balance);
        }
    }

    public void checkBalance() {
        System.out.println("Current balance is " + balance);
    }
}
