# unit-4-2-assignment

## To compile code
All code must be compiled before you can run it.  To compile means that you are converting your C++ code into a language that the computer can understand (e.g., binary).  To compile C++ code, run the following command in a terminal:
```
g++ fileName.cpp -o outFileName
```
This tells the C++ compiler to compile your file named `fileName.cpp`, and output it (`-o`) as a file named `outFileName`.

## To run code
After you have compiled the code, run your output file by running
```
./outFileName
```

## Compile and Run Example
Suppose I have a file named `classwork.cpp`.  I compile and run the file by doing
```
g++ classwork.cpp -o output
./output
```

# Calculator Assignment
* Make a calculator program using if-statements (or nested if-statements).
* Feel free to add more options
* For division, make sure that you never divide by 0.  If the user enters 0 to divide by, display an error message.
* For the square root, make sure that you do not take the square root of a negative number.  Display an error message when the user tries to take the square root of a negative number.
* Display an error message when the user enters an invalid input

# Sample Solution
```c++
#include <cmath>     // std::abs, std::sqrt, std::pow
#include <cstdlib>   // std::srand, std::rand
#include <ctime>     // std::time
#include <iostream>  // std::cin, std::cout, std::getline
#include <string>    // std::string

int main()
{
  std::srand(std::time(0));  // seeding our random number generator

  int user_input = 0;
  int num1;
  int num2;
  double numerator;
  double denominator;
  while (user_input != 99)
  {
    std::cout << "Welcome to C++ Calculator! Choose an option below!\n"
              << "0. Roll a dice\n"        
              << "1. Add\n"
              << "2. Subtract\n"
              << "3. Multiply\n"
              << "4. Divide\n"
              << "5. Square root\n"
              << "99. Quit\n> ";

    std::cin >> user_input;
    
    if (user_input == 0)
    {
      int random_number = (std::rand() % 6) + 1;  // random numbers between 1 and 6
      std::cout << "You rolled a " << random_number << std::endl;
    }
    else
    {
      if (user_input == 1)
      {
        std::cout << "Enter two numbers\n";
        std::cin >> num1 >> num2;
        std::cout << "Their sum is " << (num1 + num2) << std::endl;
      }
      else
      {
        if (user_input == 2)
        {
          std::cout << "Enter two numbers\n";
          std::cin >> num1 >> num2;
          std::cout << "Their difference is " << (num1 - num2) << std::endl;
        }
        else
        {
          if (user_input == 3)
          {
            std::cout << "Enter two numbers\n";
            std::cin >> num1 >> num2;
            std::cout << "Their product is " << (num1 * num2) << std::endl;
          }
          else
          {
            if (user_input == 4)
            {
              std::cout << "Enter two numbers\n";
              std::cin >> numerator >> denominator;
              if (denominator == 0)
              {
                std::cout << "Error: Division by zero is not allowed.\n";
              }
              else
              {
                std::cout << "Their quotient is " << (numerator / denominator) << std::endl;
              }
            }
            else
            {
              if (user_input == 5)
              {
                std::cout << "Enter a number\n";
                std::cin >> num1;
                if (num1 < 0)
                {
                  std::cout << "Error: Cannot compute square root of a negative number.\n";
                }
                else
                {
                  std::cout << "The square root of " << num1 << " is " << sqrt(num1) << std::endl;
                }
              }
              else
              {
                if (user_input != 99)
                {
                  std::cout << "Invalid option, please choose again.\n";
                }  // end if invalid input
              }  // end if-else choice 5
            }  // end if-else choice 4
          }  // end if-else choice 3
        }  // end if-else choice 2
      }  // end if-else choice 1
    }  // end if-else choice 0
  }  // end while

  std::cout << "Goodbye!\n";
  return 0;
}
```
