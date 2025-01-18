# Regex


using System;
using System.Text.RegularExpressions;

class Program
{
    static void Main()
    {
        Console.WriteLine("Enter your password:");
        string password = Console.ReadLine();

        if (IsValidPassword(password))
        {
            Console.WriteLine("Password is valid.");
        }
        else
        {
            Console.WriteLine("Password is invalid. Make sure it meets the criteria:");
            Console.WriteLine("1. At least 8 characters long");
            Console.WriteLine("2. Contains uppercase and lowercase letters");
            Console.WriteLine("3. Includes at least one number");
            Console.WriteLine("4. Has at least one special symbol");
        }
    }

    static bool IsValidPassword(string password)
    {
        if (password.Length < 8) return false;
        if (!Regex.IsMatch(password, "[A-Z]")) return false;
        if (!Regex.IsMatch(password, "[a-z]")) return false;
        if (!Regex.IsMatch(password, "[0-9]")) return false;
        if (!Regex.IsMatch(password, "[^a-zA-Z0-9]")) return false;
        return true;
    }
  }
