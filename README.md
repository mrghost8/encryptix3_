# encryptix3_
import java.util.Scanner;
//ATM Machine Interface using Class ATM &BankAccount which includes mothods like Deposite,Withdraw&Balancecheck
class ATM 
{
    private BankAccountacc;
    public ATM(BankAccountacc)
    {
this.acc=acc;
    }
    void bank_process()
    {
        Scanner sc = new Scanner(System.in);
boolean running= true;
        while(running)
        {
System.out.println("------WELCOME TO ATM------");
System.out.println("     1. Check Balance ");
System.out.println("     2. Deposit");
System.out.println("     3. Withdraw ");
System.out.println("     4. Exit ");
System.out.print("Enter your choice: ");

          int opt = sc.nextInt();
          switch(opt)
          {
              case 1: System.out.println("Your Current Balance in the Account is Rs."+acc.getBalance());
              break;
              case 2: System.out.print("Enter the amount to Deposit : Rs.");
              double Amount_deposit = sc.nextDouble();
acc.Deposit(Amount_deposit);
              break;
              case 3: System.out.print("Enter the amount to Withdraw : Rs.");
              double Amount_withdraw = sc.nextDouble();
acc.Withdraw(Amount_withdraw);
              break;
              case 4: running = false;
System.out.println("THANK YOU FOR VISITING US !");
              break;
default:System.out.println("You have entered wrong choice.");
          }
        }
sc.close();
    }
}
class BankAccount
{
    private double bal;
BankAccount(double initial_bal)
    {
this.bal= initial_bal;
    }
    double getBalance(){
        return bal;
    }
    void Deposit(double amount){
        if(amount>0){
bal += amount;
System.out.println("Your amount Rs."+amount+ " is deposited successfully!");
}else{
System.out.println("Please enter positive amount");
        }
    }
    void Withdraw(double amount){
        if(amount>0 && amount<=bal){
bal -= amount;
System.out.println("Your amount Rs."+amount+ " is withdraw successfully!");
}else{
System.out.println("You do not have sufficient balance to Withdraw");
        }
    }
}
public class Main{
    public static void main(String[] args){
BankAccount BA = new BankAccount(12000.0);
        ATM atm = new ATM(BA);
atm.bank_process();
    }
}
