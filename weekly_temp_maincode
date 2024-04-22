import java.util.ArrayList;
import java.util.Scanner;

public class WeeklyTemperature {
    public static void main(String[] args) {
        String[] weekDays = {"Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday"};
        ArrayList<Double> temperatures = new ArrayList<>(7);
//create an empty list to store 7 variables
        Scanner scanner = new Scanner(System.in);

       
        System.out.println("Enter the average temperature for each day:");
        for (String day : weekDays) {
            System.out.print(day + ": ");
            temperatures.add(scanner.nextDouble()); //read user input as double value and add to arraylist
        }

        while (true) { //beginning of main loop
            System.out.print("Enter a day to get the temperature, 'week' for the weekly average, or 'exit' to quit: ");
            String input = scanner.next().toLowerCase();

            if (input.equals("exit")) {
                System.out.println("Goodbye!");
                break;
            }//only two main loop possibilites, everything else can else

            if (input.equals("week")) {
                double total = 0;
                for (double temp : temperatures) {
                    total += temp;
                }
                double weeklyAverage = total / temperatures.size();
                System.out.printf("Weekly average temperature: %.2f°C\n", weeklyAverage);
            } else {
                boolean found = false;
                for (int i = 0; i < weekDays.length; i++) {
                    if (weekDays[i].toLowerCase().equals(input)) {
                        System.out.printf("%s's temperature: %.2f°C\n", weekDays[i], temperatures.get(i));
                        found = true;
                        break;
                    }
                }
                if (!found) {
                    System.out.println("Invalid day. Please enter a valid day.");
                }
            }
        }

        scanner.close();  
    }
}
