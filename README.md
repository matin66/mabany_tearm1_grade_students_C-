using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace quiz
{
    internal class Program
    {
        static void menu()
        {
            Console.WriteLine("********** Quiz Number 2 **********\n\n\n");
            Console.WriteLine("1 - Enter Students Num \n");
            Console.WriteLine("2 - Print Students Nums Average \n");
            Console.WriteLine("3 - Enter Students Num Max/Min \n");
            Console.WriteLine("4 - Exit from Program \n\n\n");

            ChangeTextColor("Please Enter your Command ( 1-4 digit ) :", ConsoleColor.Red);
        }
        static void ChangeTextColor(string text, ConsoleColor color)
        {
            Console.ForegroundColor = color;
            Console.WriteLine(text);
            Console.ResetColor();
        }
        static void Main(string[] args)
        {
            menu();
            int number = Convert.ToInt32(Console.ReadLine());
            Console.Clear();
            Console.WriteLine("Enter the Students count: ");
            int student = Convert.ToInt32(Console.ReadLine());
            double[,] student_grade = new double[student, 3];

            while (number != 4)
            {

                switch (number)
                {
                    case 1: // insert the number of student 
                        Console.Clear();

                        for (int i = 0; i < student_grade.GetLength(0); i++)
                        {
                            Console.WriteLine("*** Number of Students {0} ***", i + 1);
                            Console.WriteLine("Enter Grades for Student {0}", i + 1);
                            for (int grade = 0; grade < 3; grade++)
                            {
                                Console.WriteLine("Enter grade {0} _ {1}", i + 1, grade + 1);
                                student_grade[i, grade] = Convert.ToDouble(Console.ReadLine());
                            }
                        }

                        ChangeTextColor("************************ insert information successful ************************", ConsoleColor.Green);
                        Console.WriteLine("\n************************ To return back press any key : ... ");
                        Console.ReadKey();
                        Console.Clear();
                        break;
                    case 2: // Average of students


                        ChangeTextColor("************************ Average of Students ************************", ConsoleColor.Green);
                        for (int i = 0; i < student_grade.GetLength(0); i++)
                        {
                            double total = 0;
                            for (int grade = 0; grade < 3; grade++)
                            {
                                Console.WriteLine("count of studnet [ {0} ] of students grade [ {1} ] is : {2} ", i + 1, grade + 1, student_grade[i, grade]);
                                total += student_grade[i, grade];
                            }
                            Console.WriteLine("avrage number of students [ {0} ] is : {1} ", i + 1, total / 3);
                        }
                        Console.WriteLine("\n************************ To return back press any key : ... ");
                        Console.ReadKey();
                        Console.Clear();
                        break;

                    case 3: // max or min

                        ChangeTextColor("************************ max or min ************************", ConsoleColor.Green);
                        for (int i = 0; i < student_grade.GetLength(0); i++)
                        {
                            double min = student_grade[i, 0];
                            for (int grade = 0; grade < 3; grade++)
                            {
                                //Console.WriteLine("count of studnet [ {0} ] of students grade [ {1} ] is : {2} ", i + 1, grade + 1, student_grade[i, grade]);
                                if (student_grade[i, grade] < min)
                                {
                                    min = student_grade[i, grade];
                                }

                            }
                            Console.WriteLine("min number of studen [ {0} ] is : {1}", i + 1, min);


                        }
                        Console.WriteLine("\n");
                        for (int i = 0; i < student_grade.GetLength(0); i++)
                        {
                            double max = student_grade[i, 0];
                            for (int grade = 0; grade < 3; grade++)
                            {
                                //Console.WriteLine("count of studnet [ {0} ] of students grade [ {1} ] is : {2} ", i + 1, grade + 1, student_grade[i, grade]);
                                if (student_grade[i, grade] > max)
                                {
                                    max = student_grade[i, grade];
                                }

                            }
                            Console.WriteLine("max number of studen [ {0} ] is : {1}", i + 1, max);

                        }
                        Console.WriteLine("\n************************ To return back press any key : ... ");
                        Console.ReadKey();
                        Console.Clear();
                        break;
                    default:

                        Console.WriteLine("your input is [ {0} ]" , number);
                        ChangeTextColor("command numberinserte is worng !!! please selec 1-4 digit ...", ConsoleColor.Red);
                        Console.WriteLine("for back the main space please entet the key ...");
                        Console.ReadKey();
                        Console.Clear();

                        break;
                }
                menu();
                number = Convert.ToInt32(Console.ReadLine());
                Console.Clear();
            }

            if (number == 4)
            {
                
                ChangeTextColor("thank you for using my program ...", ConsoleColor.Blue);
            }
        }
    }
}

//Bio for the Quiz Program

// Bio: This program is a C# console application developed as part of a university assignment
// for the Fundamentals of Computer Science course. It serves as a tool for managing and analyzing
// student grades, allowing users to enter the number of students, calculate and print average grades,
// and find the maximum and minimum grades for each student. The application provides a menu-driven
// interface and employs a 2D array to store student grades. Colored text messages enhance user interaction,
// and the program includes error handling for incorrect input. Developed for educational purposes,
// this quiz program showcases basic console-based interaction and array manipulation in C#.


// The program utilizes a 2D array to store student grades and includes error handling for
// incorrect user input. It displays messages in different colors to enhance user interaction
// and provides a user-friendly experience.

// The main functionality includes:
// 1.Entering the number of students and their grades.
// 2. Calculating and printing the average grades for each student.
// 3. Finding and displaying the maximum and minimum grades for each student.
// 4. Allowing the user to exit the program.

// Overall, the Quiz Program demonstrates basic console-based interaction and array manipulation
// in C#, provi
