/** ATM Interface */
 
import java.util.*;
class BankAccount 
{
  String name;
  String username;
  String password;
  String accountno;
  String transHistory = "";
  float balance = 10000;
  int transaction = 0; 
  
  public void signup()
  {
    Scanner scan = new Scanner(System.in);
    System.out.println("\nEnter your Name - ");
    this.name = scan.nextLine();
    System.out.println("\nEnter your User name - ");
    this.username = scan.nextLine();
    System.out.println("\nEnter your Password - ");
    this.password = scan.nextLine();
    System.out.println("\nEnter your Account number - ");
    this.accountno = scan.nextLine();
    System.out.println("\nRegistration completed..Kindly login..");
    System.out.println("\n**************************************************");
  }
  
  public boolean login()
  {
    boolean isLogin = false;
    Scanner scan = new Scanner(System.in);
    while( !isLogin )
    {
      System.out.println("\nEnter your Username - ");
      String Username = scan.nextLine();
      if( Username.equals(username) )
      {
        while( !isLogin )
        {
          System.out.println("\nEnter your Password - ");
          String Password = scan.nextLine();
          if( Password.equals(password)) 
          {
            System.out.println("\nLogin successfull..!!");
            isLogin = true; 
          }
          else
          {
            System.out.println("\nIncorrect password");
          } 
        }
      }
      else
      {
        System.out.println("\nUsername not found");
      }    
    }  
    return isLogin;
  }
  
  public void withdraw()
  {
    System.out.println("\nEnter amount to withdraw - ");
    Scanner scan = new Scanner(System.in);
    float amount = scan.nextFloat();
    try
    {
      if(balance >= amount)
      {
        transaction++;
        balance = balance - amount;
        System.out.println("\nWithdraw Successfully"); 
        String str = amount + "Rs Withdraw\n";
        transHistory = transHistory.concat(str);        
      }
      else
      {
        System.out.println("\nInsufficient Balance");       
      }
    }
    catch (Exception e){
    }
    System.out.println("\n**************************************************");
  }
  
  public void deposit()
  {
    System.out.println("\nEnter amount to deposit - ");
    Scanner scan = new Scanner(System.in);
    float amount = scan.nextFloat();
    try
    {
      if(amount <= 10000)
      {
        transaction++;
        balance = balance + amount;
        System.out.println("\nSuccessfully Deposited"); 
        String str = amount + "Rs deposited\n";
        transHistory = transHistory.concat(str);        
      }
      else
      {
        System.out.println("\nSorry....Limit is 10000.00");       
      }
    }
    catch (Exception e){
    } 
    System.out.println("\n**************************************************");
  }
  
  public void transfer()
  {
    Scanner scan = new Scanner(System.in);
    System.out.println("\nEnter Receipent's Name - ");
    String receipent = scan.nextLine();
    System.out.println("\nEnter amount to transfer - ");
    float amount = scan.nextFloat();  
    try
    {
      if(balance >= amount)
      {
        if(amount <= 50000f)
        {
          transaction++;
          balance = balance - amount;
          System.out.println("\nSuccessfully transfered to "+receipent); 
          String str = amount + "Rs transfered to " +receipent+ "\n";
          transHistory = transHistory.concat(str);        
        }
        else
        {
          System.out.println("\nSorry....Limit is 50000.00");       
        }
      }
      else
      {
        System.out.println("\nInsufficient Balance");       
      }
    }
    catch (Exception e){
    }
    System.out.println("\n**************************************************");
  }
  
  public void checkBalance()
  {
    System.out.println("\n" +balance+ " Rs");
    System.out.println("\n**************************************************");
  }
  
  public void transHistory()
  {
    if(transaction == 0)
    {
      System.out.println("\nEmpty");
    }
    else
    {
      System.out.println("\n" + transHistory);
    }
    System.out.println("\n**************************************************");
  }
}


public class AtmInterface
{
  public static int takeIntegerInput(int limit)
  {
    int input = 0;
    boolean flag = false;
    
    while( !flag )
    {
      try
      {
        Scanner scan = new Scanner(System.in);
        input = scan.nextInt();
        flag = true;
        
        if(flag && input > limit || input < 1)
        {
          System.out.println("Choose the number between 1 to " +limit);
          flag = false;
        }
      }
      catch (Exception e)
      {
        System.out.println("Enter only integer value");
        flag = false;
      }
    };
    return input;
  }
  
  public static void main(String args[])
  {
    System.out.println("\n*************WELCOME TO BOI ATM SYSTEM*************\n");
    System.out.println("1.Register \n2.Exit");
    System.out.println("Enter your choice - ");
    int choice = takeIntegerInput(2);
    
    if (choice == 1) 
    {
      BankAccount b = new BankAccount();
      b.signup();
      while(true)
      {
        System.out.println("\n1.Login \n2.Exit");
        System.out.println("Enter your choice - ");
        int ch = takeIntegerInput(2);
        if(ch == 1)
        {
          if(b.login())
          {
            System.out.println("\n\n****************WELCOME BACK " +b.name+ "****************\n");
            boolean isFinished = false;
            while (!isFinished) 
            { 
              System.out.println("\n1.Withdraw \n2.Deposit \n3Transfer \n4.Check Balance \n5.Transaction History \n6.Exit");
              System.out.println("\nEnter your choice - ");
              int c = takeIntegerInput(6);
              switch(c)
              {
                case 1:
                b.withdraw();
                break;
                case 2:
                b.deposit();
                break;
                case 3:
                b.transfer();
                break;
                case 4:
                b.checkBalance();
                break;
                case 5:
                b.transHistory();
                break;
                case 6:
                isFinished = true;
                break;
              } 
            }
          }
        }
        else
        {
          System.exit(0);
        }
      }
    } 
    else
    {
      System.exit(0);
    }
  }
}  
