public class Calculator {

    public int add(int a, int b) {
        return a + b;
    }

    public int subtract(int a, int b) {
        return a - b;
    }

    public int multiply(int a, int b) {
        return a * b;
    }

    public int divide(int a, int b) {
        return a / b;
    }
}



import static org.junit.jupiter.api.Assertions.*;
import org.junit.jupiter.api.Test;

public class CalculatorTest {

    Calculator calc = new Calculator();

    @Test
    void testAdd() {
        assertEquals(5, calc.add(2, 3));
    }

    @Test
    void testSubtract() {
        assertEquals(1, calc.subtract(3, 2));
    }

    @Test
    void testMultiply() {
        assertEquals(6, calc.multiply(2, 3));
    }

    @Test
    void testDivide() {
        assertEquals(2, calc.divide(6, 3));
    }
}







public class Greeting {

    public String getGreeting(String name) {
        return "Hello " + name;
    }
}




import static org.junit.jupiter.api.Assertions.*;
import org.junit.jupiter.api.Test;

public class GreetingTest {

    Greeting g = new Greeting();

    @Test
    void testGreeting() {
        assertEquals("Hello Rakshitha", g.getGreeting("Rakshitha"));
    }
}





public class LinearSearch {

    public int search(int[] arr, int key) {
        for(int i = 0; i < arr.length; i++) {
            if(arr[i] == key) {
                return i;
            }
        }
        return -1;
    }
}



import static org.junit.jupiter.api.Assertions.*;
import org.junit.jupiter.api.Test;

public class LinearSearchTest {

    LinearSearch ls = new LinearSearch();

    @Test
    void testSearchFound() {
        int[] arr = {10, 20, 30};
        assertEquals(1, ls.search(arr, 20));
    }

    @Test
    void testSearchNotFound() {
        int[] arr = {10, 20, 30};
        assertEquals(-1, ls.search(arr, 40));
    }
}



public class HighestNumber {

    public int findHighest(int a, int b, int c) {
        int max = a;
        if(b > max) max = b;
        if(c > max) max = c;
        return max;
    }
}



import static org.junit.jupiter.api.Assertions.*;
import org.junit.jupiter.api.Test;

public class HighestNumberTest {

    HighestNumber h = new HighestNumber();

    @Test
    void testHighest() {
        assertEquals(50, h.findHighest(10, 50, 30));
    }
}



public class BankAccount {

    private double balance = 0;

    public double getBalance() {
        return balance;
    }

    public void deposit(double amount) {
        balance += amount;
    }

    public void withdraw(double amount) {
        if(amount <= balance) {
            balance -= amount;
        }
    }
}



import static org.junit.jupiter.api.Assertions.*;
import org.junit.jupiter.api.Test;

public class BankAccountTest {

    BankAccount acc = new BankAccount();

    @Test
    void testDeposit() {
        acc.deposit(100);
        assertEquals(100, acc.getBalance());
    }

    @Test
    void testWithdraw() {
        acc.deposit(100);
        acc.withdraw(40);
        assertEquals(60, acc.getBalance());
    }

    @Test
    void testWithdrawMoreThanBalance() {
        acc.deposit(50);
        acc.withdraw(100);
        assertEquals(50, acc.getBalance()); // no change
    }
}






