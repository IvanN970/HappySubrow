using System;
using System.Text;
using System.Collections.Generic;
using System.Linq;
namespace HappySubrow
{
    class Program
    {
        static void CreateRow(List<int> row,int length)
        {
            int number;
            while(length!=0)
            {
                Console.WriteLine("Enter number:");
                number = int.Parse(Console.ReadLine());
                row.Add(number);
                length--;
            }
        }
        static void ExtractSubRowsEqualToNumber(List<int> row,int n,SortedDictionary<int,List<List<int>>> dict)
        {
            List<int> currentRow = new List<int>();
            int count;
            for(int i=0;i<row.Count;i++)
            {
                count = i;
                while(true)
                {
                     if(IsSubRowSumEqualToNumber(currentRow, n)==true)
                      {
                        if(dict.ContainsKey(currentRow.Count)==false)
                        {
                            dict.Add(currentRow.Count, new List<List<int>> { new List<int>(currentRow) });
                        }
                        else
                        {
                            dict[currentRow.Count].Add(new List<int>(currentRow));
                        }
                      }
                      if(count==row.Count)
                      {
                        break;
                      }
                    currentRow.Add(row[count]);
                    count++;
                }
                currentRow.Clear();
            }
        }
        static bool IsSubRowSumEqualToNumber(List<int> row,int n)
        {
            int sum = 0;
            for(int i=0;i<row.Count;i++)
            {
                sum = sum + row[i];
            }
            return sum == n;
        }
        static void PrintResult(SortedDictionary<int,List<List<int>>> dict)
        {
            int counter = 0;
            foreach (KeyValuePair<int, List<List<int>>> key in dict.Reverse())
            { 
                foreach (var k in key.Value)
                {
                    foreach (int p in k)
                    {
                        Console.Write(p + " ");
                    }
                    Console.WriteLine();
                    counter++;
                    if (counter == 10)
                    {
                        break;
                    }
                }
                if (counter == 10)
                {
                    break;
                }
            }
        }
        static void Main()
        {
            List<int> row = new List<int>();
            SortedDictionary<int, List<List<int>>> dict = new SortedDictionary<int, List<List<int>>>();
            int n, length;
            Console.WriteLine("Enter length of the row:");
            length = int.Parse(Console.ReadLine());
            Console.WriteLine("Enter sum of numbers:");
            n = int.Parse(Console.ReadLine());
            CreateRow(row, length);
            ExtractSubRowsEqualToNumber(row, n,dict);
            PrintResult(dict);
        }
    }
}
