# Revenue-Calculator-in-JAVA
import java.util.Scanner;

public class RevenueCalculator
 {
    public static void main(String[] args) 
    {
        Scanner scanner = new Scanner(System.in);

        // Sample data (replace with your actual data)
        String[][] data = 
        {
            {"January", "North", "Smartphones", "1200", "24000"},
            {"January", "South", "Laptops", "900", "18000"},
            {"February", "North", "Laptops", "1000", "20000"},
            {"February", "South", "Smartphones", "1100", "23000"}
        };

        // Get user input for month and region
        System.out.print("Enter the month (January or February): ");
        String month = scanner.nextLine().toLowerCase();

        System.out.print("Enter the region (North or South): ");
        String region = scanner.nextLine().toLowerCase();

        // Find the matching data and calculate revenue
        double revenue = 0;
        for (String[] row : data)
         {
            if (row[0].equalsIgnoreCase(month) && row[1].equalsIgnoreCase(region))
             {
                revenue = Double.parseDouble(row[4]);
                break;
            }
        }

        // Display the result
        if (revenue > 0) 
        {
            System.out.println("Revenue for " + region + " in " + month + ": $" + revenue);
        } else {
            System.out.println("No data found for the specified month and region.");
        }
    }
}
