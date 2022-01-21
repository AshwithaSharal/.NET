# .NET
<br>
using System;<br>
namespace exercises<br>
{<br>
    class BinaryTriangle<br>
    {<br>
        static void Main(string[] args)
        {
            int number, digit = 1;
            Console.WriteLine("\n Enter the number of lines:");
            number = Convert.ToInt32(Console.ReadLine());
            for (int i = 1; i <= number; i++)
            {
                {
                    for (int space = number - i; space > 0; space--)
                    {
                        Console.Write(" ");
                    }
                    for (int j = 0; j < i; j++)
                    {
                        Console.Write(digit + " ");
                        digit = (digit == 1) ? 0 : 1;
                    }
                    Console.Write("\n");

                }
            }

        }
    }
}
Output:
![Screenshot 2022-01-21 062714](https://user-images.githubusercontent.com/98145023/150477760-3a4631a3-a5e3-40ef-993b-a28244da5759.png)

