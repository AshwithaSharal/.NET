# .NET
**1)**
<br>
using System;<br>
namespace exercises<br>
{<br>
    class BinaryTriangle<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            int number, digit = 1;<br>
            Console.WriteLine("\n Enter the number of lines:");<br>
            number = Convert.ToInt32(Console.ReadLine());<br>
            for (int i = 1; i <= number; i++)<br>
            {<br>
                {<br>
                    for (int space = number - i; space > 0; space--)<br>
                    {<br>
                        Console.Write(" ");<br>
                    }<br>
                    for (int j = 0; j < i; j++)<br>
                    {<br>
                        Console.Write(digit + " ");<br>
                        digit = (digit == 1) ? 0 : 1;<br>
                    }<br>
                    Console.Write("\n");<br>
                    }<br>
                    }<br>
         }<br>
    }<br>
}<br>
Output:


![image](https://user-images.githubusercontent.com/98145023/150480612-1fa6983f-cf2c-4369-82a0-381897fdf1e5.png)

<br><br><br><br><br><br><br><br><br>

2)
using System;<br>
namespace exercises<br>
{<br>
    class AmicableNumber<br>
    {<br>
        static void Main(string []args)<br>
        {<br>
            int num1, num2, sum1 = 0, sum2 = 0;<br>
            Console.Write("\n-----AMICABLE NUMBERS-----\n");<br>
            Console.WriteLine("\n Enter the first number:");<br>
            num1 = Convert.ToInt32(Console.ReadLine());<br>
            Console.WriteLine("\n Enter the second number:");<br>
            num2 = Convert.ToInt32(Console.ReadLine());<br>
            for (int i = 1;i< num1;i++)<br>
            {<br>
                if(num1 % i==0)<br>
                {<br>
                    sum1+=i;<br>
                }<br>
            }<br>
            for (int i= 1; i < num2; i++)<br>
            {<br>
                if (num2 % i == 0)<br>
                { sum2 += i;<br>
                }<br>
            }<br>
            if(sum1==num2 && sum2==num1)<br>
            {<br>
                Console.WriteLine("\n The numbers {0} and {1} are amicable.", num1, num2);<br>
            }<br>
            else<br>
            {<br>
                Console.WriteLine("\n The numbers {0}  and {1} are not amicable", num1, num2);<br>
            }<br>
        }<br>
    }<br>
}<br>

Output:<br>
![image](https://user-images.githubusercontent.com/98145023/150485219-c3b2526e-e7a8-44a5-88e1-00112048f123.png)<br>
![image](https://user-images.githubusercontent.com/98145023/150485471-4ef50c93-d303-48bb-9c1a-38cbfc4a1b27.png)







