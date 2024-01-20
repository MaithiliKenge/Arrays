# Arrays
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
