# java-bankaccount
class BankAccount {
    private double balance;
    
    public BankAccount(double initialBalance) {
        if (initialBalance >= 0) {
            balance = initialBalance;
        } else {
            balance = 0;
            System.out.println("Initial balance is invalid. Setting balance to 0.");
        }
    }
    
    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
            System.out.println("Deposited: " + amount);
        } else {
            System.out.println("Invalid deposit amount.");
        }
    }
    
    public void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
            System.out.println("Withdrew: " + amount);
        } else {
            System.out.println("Invalid withdrawal amount or insufficient funds.");
        }
    }
    
    public double getBalance() {
        return balance;
    }
    
    public static void main(String[] args) {
        BankAccount account = new BankAccount(1000);
        
        System.out.println("Initial Balance: " + account.getBalance());
        
        account.deposit(500);
        System.out.println("Balance after deposit: " + account.getBalance());
        
        account.withdraw(200);
        System.out.println("Balance after withdrawal: " + account.getBalance());
        
        account.withdraw(2000); // Invalid withdrawal
    }
}
