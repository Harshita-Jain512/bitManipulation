# bitManipulation
if you want to check a number is prime or not 
suppose a number is num then
first check the number is greater then 1 or not 
the check it only divisible by 1 and itself ,
for second condition use
for(int i = 2; i<= Math.sqrt(num); i++){
if(num % i == 0){
isprime = false;
break;
}
}
we run upto Math.sqrt(num) because - 
Thought process:

Divisors come in pairs

Example for 36:

1 × 36
2 × 18
3 × 12
4 × 9
6 × 6  ← √36


👉 After √num, factors just repeat in reverse
👉 If no divisor is found before √num, none will exist after

import java.util.Scanner;

public class PrimeCheck {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a number: ");
        int num = sc.nextInt();

        boolean isPrime = true;

        // Numbers less than or equal to 1 are not prime
        if (num <= 1) {
            isPrime = false;
        } else {
            // Check divisibility from 2 to sqrt(num)
            for (int i = 2; i <= Math.sqrt(num); i++) {
                if (num % i == 0) {
                    isPrime = false;
                    break;
                }
            }
        }

        if (isPrime) {
            System.out.println(num + " is a Prime number.");
        } else {
            System.out.println(num + " is NOT a Prime number.");
        }

        sc.close();
    }
}


Checking till num - 1 is wasteful

Checking till √num is efficient and smart
