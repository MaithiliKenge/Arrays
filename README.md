# Arrays Write a program to read an integer 1D array containing 8 bits (0s, 1s) of an unsigned binary integer. The program should print the decimal value for the integer.
import java.util.Scanner;
public class Conversion {
public static void main(String[] args) {
Scanner sc = new Scanner(System.in);
int[] Arr = new int[8];
System.out.println("Enter 8 bits:");
     for (int i = 0; i < 8; i++) {
         Arr[i] = sc.nextInt();
	      if (Arr[i] != 0 && Arr[i] != 1) {
              System.out.println("Please enter valid input.");
              return;
           }
       }
int dec = 0;
     for (int i = 7; i >= 0; i--) {
         dec += Arr[i] * Math.pow(2, 7 - i);
       }
       System.out.println("Decimal value: " + dec);
   }
}

**#Currency notes are available in the following seven denominations: Rs. 1, Rs. 2, Rs. 5, Rs. 10, Rs. 20, Rs.50, and Rs. 100.
You will first read an integer array (named purse [7]) of seven elements, where the array elements represents the number of notes of each denomination (in increasing order of denomination) available with you. You are also given an amount of money to be paid using these notes. The amount will be less than Rs. 1000. You have to pay the amount using minimum number of notes. Print the number of notes of each denomination which you will use to pay the amount. If the amount cannot be paid using the available notes, print “Failed to Pay”.**

import java.util.Scanner;
public class PayAmount {
public static void main(String[] args) {
Scanner sc = new Scanner(System.in);
int[] purse = new int[7];
System.out.println("Enter the number of notes of each denomination (1, 2, 5, 10, 20, 50, 100):");
for (int i = 0; i < 7; i++) {
     purse[i] = sc.nextInt();
}
System.out.println("Enter the amount to be paid:");
int amount = sc.nextInt();
int[] notesUsed = minNotes(purse, amount);
if (notesUsed == null) {
  System.out.println("Failed to Pay");
} 
else {
  System.out.println("Notes used:");
  for (int i = 0; i < 7; i++) {
      System.out.println(denominations[i] + " Rs notes: " + notesUsed[i]);
      }
    }
 }

static int[] denominations = {1, 2, 5, 10, 20, 50, 100};
public static int[] minNotes(int[] purse, int amount) 
{
   int[] notes = new int[7];
   for (int i = 6; i >= 0; i--) {
   while (amount >= denominations[i] && purse[i] > 0) {
       amount -= denominations[i];
       purse[i]--;
       notes[i]++;
    }
 }
return amount == 0 ? notes : null;
   }
}
