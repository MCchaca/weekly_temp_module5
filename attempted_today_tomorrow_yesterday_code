import java.util.ArrayList;
import java.util.Scanner;

import java.time.DayOfWeek;
import java.time.LocalDate;
import java.time.format.DateTimeFormatter;  

public class WeeklyTemperature {
    public static void main(String[] args) {
        String[] weekDays = {"Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday"};
        
        ArrayList<Double> temperatures = new ArrayList<>(7);
//create an empty list to store 7 variables
        Scanner scanner = new Scanner(System.in);
        LocalDate today = LocalDate.now();
        System.out.println("Current system date: " + today);
        DayOfWeek dayOfWeek = today.getDayOfWeek();
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("EEEE, dd-MM-yyyy");
        System.out.println("Today is: " + today.format(formatter));
        int todayIndex = today.getDayOfWeek().getValue() - 1;  // 0 for Monday, 6 for Sunday

        System.out.println("Enter the average temperature for each day:");
        for (String day : weekDays) {
            System.out.print(day + ": ");
            temperatures.add(scanner.nextDouble()); //read user input as double value and add to arraylist
        }

        while (true) { //beginning of main loop
            System.out.print("Enter a day to get the temperature, 'week' for the weekly average, or 'exit' to quit: ");
            String input = scanner.next().toLowerCase();
            
            System.out.print("Enter 'yesterday', 'today', 'tomorrow', a day of the week, 'week', or 'exit' to quit: ");
            String input1 = scanner.next().trim().toLowerCase();
            
            if (input1.equals("exit")) {
                System.out.println("Goodbye!");
                break;
            }
            if (input1.equals("yesterday")) {  
                int yesterdayIndex = (todayIndex - 1 + 7) % 7;
                System.out.printf("The temperature yesterday (%s) was: %.2f°C\n", weekDays[yesterdayIndex], temperatures.get(yesterdayIndex));
            } else if (input1.equals("today")) {  
                System.out.printf("The temperature today (%s) is: %.2f°C\n", weekDays[todayIndex], temperatures.get(todayIndex));
            } else if (input1.equals("tomorrow")) {  
                int tomorrowIndex = (todayIndex + 1) % 7; 
                System.out.printf("The temperature tomorrow (%s) will be: %.2f°C\n", weekDays[tomorrowIndex], temperatures.get(tomorrowIndex));

            if (input1.equals("week")) {
                double total = 0;
                for (double temp : temperatures) {
                    total += temp;
                }
                double weeklyAverage = total / temperatures.size();
                System.out.printf("Weekly average temperature: %.2f°C\n", weeklyAverage);
            } else {
                boolean found = false;
                for (int i = 0; i < weekDays.length; i++) {
                    if (weekDays[i].toLowerCase().equals(input1)) {
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
}}
