# assignment6
//Bryce Shelton
//CSE 1321L
using System;
class Assignment6A
{
    static int initialize(int[] nums)
    {
        int i = 0;
        while (true)
        {
            Console.Write("Enter a number or -1 to finish: ");
            string n = Console.ReadLine();
            int number = Int32.Parse(n);
            if (number == -1)
            {
                break;
            }
            nums[i] = number;
            i++;
        }
        return i;
    }
    static void print(int[] nums, int size)
    {
        for (int i = 0; i < size; i++)
        {
            if (i == 0)
            {
                Console.Write("|{0}|", nums[i]);
            }
            else
            {
                Console.Write("{0}|", nums[i]);
            }
        }
    }
    static int findMin(int[] nums, int size)
    {
        int min = nums[0];
        for (int i = 0; i < size; i++)
        {
            if (nums[i] < min)
            {
                min = nums[i];
            }
        }
        return min;
    }
    static int findMax(int[] nums, int size)
    {
        int max = nums[0];
        for (int i = 0; i < size; i++)
        {
            if (nums[i] > max)
            {
                max = nums[i];
            }
        }
        return max;
    }
    static int findSum(int[] nums, int size)
    {
        int sum = 0;
        for (int i = 0; i < size; i++)
        {
            sum += nums[i];
        }
        return sum;
    }
    static void b()
    {
        int[] numbers = new int[100];
        int length = initialize(numbers);
        print(numbers, length);
        Console.WriteLine("\nMin is: " + findMin(numbers, length));
        Console.WriteLine("Max is: " + findMax(numbers, length));
        Console.WriteLine("Sum is: " + findSum(numbers, length));
    }

    class Program
    {
        static void Main()
        {
            int size = 100;
            int count = 0;
            int index = 0;
            int[] A = new int[size];
            int[] B = new int[size];
            for (int i = 0; i < size; i++)
            {
                Console.Write("Enter a number or -1 to finish: ");
                A[i] = int.Parse(Console.ReadLine());
                count++;
                if (A[i] == -1)
                {
                    break;
                }
            }
            Console.Write("|");
            for (int i = 0; i < count - 1; i++)
            {
                Console.Write(A[i] + "|");
            }
            for (int i = 0; i < count - 1; i++)
            {
                int temp = A[i];
                B[temp]++;
            }
            int max = B[0];
            for (int i = 0; i < size; i++)
            {
                if (B[i] > max)
                {
                    max = B[i];
                    index = i;
                }
            }
            Console.WriteLine("\nThere are " + max + " occurances of " + index);
        }
    }
}
//The basis of this asssignment was to demonstrate my knowledge of array building , the source code I created in c#
//was to capture the input from the user then once they finished , by inputing -1 , the previous inputs would be shown
// as well as the occurence of the lowest number . 
