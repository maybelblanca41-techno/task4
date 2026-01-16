# calculator-
using System;

namespace CalculatorApp
{
    class Program
    {
        static void Main(string[] args)
        {
            char choice = 'Y';

            while (choice == 'Y' || choice == 'y')
            {
                // Display menu
                Console.WriteLine("Press any following key to perform an arithmetic operation:");
                Console.WriteLine("1 - Addition");
                Console.WriteLine("2 - Subtraction");
                Console.WriteLine("3 - Multiplication");
                Console.WriteLine("4 - Division");

                Console.Write("Enter your choice: ");
                int operation = int.Parse(Console.ReadLine());

                // Input values
                Console.Write("Enter Value 1: ");
                double value1 = double.Parse(Console.ReadLine());

                Console.Write("Enter Value 2: ");
                double value2 = double.Parse(Console.ReadLine());

                double result = 0;
                bool validOperation = true;

                // Switch-case to select operation
                switch (operation)
                {
                    case 1:
                        result = Add(value1, value2);
                        Console.WriteLine($"{value1} + {value2} = {result}");
                        break;

                    case 2:
                        result = Subtract(value1, value2);
                        Console.WriteLine($"{value1} - {value2} = {result}");
                        break;

                    case 3:
                        result = Multiply(value1, value2);
                        Console.WriteLine($"{value1} * {value2} = {result}");
                        break;

                    case 4:
                        if (value2 != 0)
                        {
                            result = Divide(value1, value2);
                            Console.WriteLine($"{value1} / {value2} = {result}");
                        }
                        else
                        {
                            Console.WriteLine("Error: Division by zero is not allowed.");
                        }
                        break;

                    default:
                        Console.WriteLine("Invalid choice!");
                        validOperation = false;
                        break;
                }

                // Ask user to continue
                Console.Write("Do you want to continue again (Y/N)? ");
                choice = Console.ReadLine()[0];

                Console.WriteLine();
            }
        }

        // Separate methods for each operation
        static double Add(double a, double b)
        {
            return a + b;
        }

        static double Subtract(double a, double b)
        {
            return a - b;
        }

        static double Multiply(double a, double b)
        {
            return a * b;
        }

        static double Divide(double a, double b)
        {
            return a / b;
        }
    }
}
