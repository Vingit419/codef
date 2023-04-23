

package MyShop;
public class flower {
	String name;
	int no_of_petals; 
	double price; 
	int no_of_pieces;
	double total_price;
	// No argument constructor
    	public flower() {
        this.name = "Rose";
        this.no_of_petals = 10;
        this.price = 50.0;
        this.no_of_pieces = 1;
        this.total_price = this.price * this.no_of_pieces;
    	}
    // Parameterized constructor
        public flower(String name, int no_of_petals, double price, int no_of_pieces) {
            this.name = name;
            this.no_of_petals = no_of_petals;
            this.price = price;
            this.no_of_pieces = no_of_pieces;
            this.total_price = this.price * this.no_of_pieces;
        }
               public double calculate_discount() {
	            if (this.total_price > 2000) {
	                return 200;
	            } else {
	                return 100;
	            }
	        }
	        // Display Function
	        public void display() {
	            System.out.println("Flower Name = " + this.name);
	            System.out.println("Number of Petals = " + this.no_of_petals);
	            System.out.println("Price per Piece = " + this.price);
	            System.out.println("Number of Pieces = " + this.no_of_pieces);
	            System.out.println("Total Price = " + this.total_price);
	            double discount = this.calculate_discount();
	            System.out.println("Discount = " + discount);
	            System.out.println("Price after Discount = " + (this.total_price - discount));
	        }
package MyShop;
import java.util.*;
public class AllData {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
        int choice;
        // loop for displaying menu repeatedly
        do {
            System.out.println("1. Flower");
            System.out.println("2. Customer");
            System.out.println("0. Exit");
            System.out.print("Enter your choice: ");
            choice = sc.nextInt();
                switch (choice) {
                case 1:
                    System.out.println("\nFLOWER DETAILS");
                    Scanner scanner = new Scanner(System.in);
                    System.out.print("Enter flower name = ");
                    String name = scanner.nextLine();
                    System.out.print("Enter no of petals = ");
                    int no_of_petals = scanner.nextInt();
                    System.out.print("Enter price = ");
                    double price = scanner.nextDouble();
                    System.out.print("Enter no of pieces = ");
                    int no_of_pieces = scanner.nextInt();
                    flower f = new flower(name, no_of_petals, price, no_of_pieces);
                    f.display();
                    break;
                    case 2:
                    Customer c = new Customer();
                    System.out.println("\nCUSTOMER DETAILS");
                    c.getData();
                    c.showData();
                    break;
                    case 0:
                    System.out.println("\nThank you for using our application!");
                    break;

                default:
                    System.out.println("\nInvalid choice! Please try again.");
                    break;
            }
        } while (choice != 0);

	}
