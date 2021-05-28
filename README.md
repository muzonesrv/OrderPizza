# OrderPizza
// class assignment on pizza ordering system
/* In this assignment you will finish writing a pizza ordering system. You will be completing a pizza ordering system. You can order pizza, toppings, and wings. You must calculate a subtotal, tax, and final total. I will provide shell code for you to use, each area you have to modify is commented.

In the main function calculate and print the subtotal, tax, and total.

In the calculateSubTotal function, calculate the subtotal for ordering.

In the calculateTax function, calculate the tax for ordering.

There is a function called readValue that will allow you to read a number typed into the console, you don't have to understand this function, just use it. */


import java.io.IOException;
import java.util.Scanner;

public class OrderPizza
{
    private static final double COST_OF_PIZZA= 9.99;
    private static final double COST_OF_TOPPING= .99;
    private static final double COST_OF_WINGS= 5.99;
    private static final double TAX = 9.5;

    public static void main(String[] args)
    {
        try
        {

            Scanner console = new Scanner(System.in);

            int pizza = readValue("Pizza cost $9.99.  How many pizzas would you like?" );

            int toppings = readValue("Toppings cost $0.99 each.  How many toppings on each pizza?" );

            int wings = readValue("Wings cost $5.99.  How many orders of wings would you like?" );


            //Put code here to CALCULATE AND PRINT subtotal, tax, and total.

            double subtotal = calculateSubTotal(pizza, toppings, wings);
            double taxamt = calculateTax(subtotal);
            double total = calculateTotal(subtotal, taxamt);

            System.out.println("Subtotal " + subtotal);
            System.out.println("Tax " + taxamt);
            System.out.println("Total " + total);
        }
        catch (Exception e)
        {
            System.out.println("Unable to place order");
        }

    }


    /**
     *	Calculate the subtotal of the order
     *  @param numPizzas - Number of pizzas ordered
     *  @param numToppings - Number of toppings ordered
     *  @param wings - Number of wings ordered
     *  @return The subtotal
     **/

    public static double calculateSubTotal(int numPizzas, int numToppings, int numWings)
    {
        //Write a function to calculate the subtotal

        double subtotal = numPizzas*COST_OF_PIZZA + numToppings*COST_OF_TOPPING + numWings*COST_OF_WINGS;

        return subtotal;
    }

    /**
     *	Calculate the tax of the order
     *  @param subtotal - subtotal to calculate the tax on
     *  @return the amount of tax
     **/

    public static double calculateTax(double subtotal)
    {
        //Write code here to calculate the tax

        double calculateTax = subtotal*(TAX/100);

        return calculateTax;
    }

    /**
     *	Calculate the total of the order
     *  @param subtotal - subtotal to calculate the tax on
     *  @param tax - the amount of tax to charge
     *  @return the total of the order
     **/

    public static double calculateTotal(double subtotal, double tax)
    {
        // write code to calculate the total here.

        double calculateTotal = subtotal + tax;

        return calculateTotal;
    }

    /**
     * Reads a value in from the console, if there is an error it will return the current value
     * passed in
     * @param current - The value to return in case of an error
     * @return The value entered by the user
     */
    private static int readValue(String prompt)  throws IOException
    {
        if (!prompt.isEmpty())
        {
            System.out.println(prompt);
        }

        Scanner scanner = new Scanner(System.in);
        return scanner.nextInt();
    }



}
