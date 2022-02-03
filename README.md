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


![image](https://user-images.githubusercontent.com/98145023/150480612-1fa6983f-cf2c-4369-82a0-381897fdf1e5.png)<br><br>




5)<br><br>
using System;<br>
namespace Exercises<br>
{<br>
    class Box<br>
    {<br>
        float width;<br>
        float height;<br>
        float length;<br>
        public float Volume<br>
        {<br>
            get { return width * height * length; }<br>
        }<br>
        public Box(float width, float height, float length)<br>
        {<br>
            this.width = width;<br>
            this.height = height;<br>
            this.length = length;<br>
        }<br>
        public static float operator +(Box box1, Box box2)<br>
        {<br>
            return box1.Volume + box2.Volume;<br>
        }<br>
        public override String ToString()<br>
        {<br>
            return "box with width " + width + ",height " + height + " and length " + length;<br>
        }<br>
    }<br>
    class OperatorOverloading<br>
    {<br>
        public static void Main()<br>
        {<br>
            Box box1 = new Box(10, 20, 30);<br>
            Box box2 = new Box(25, 32, 15);<br>
            Console.WriteLine("Volume of {0} is :{1}", box1, box1.Volume);<br>
            Console.WriteLine("Volume of {0} is :{1}", box2, box2.Volume);<br>
            Console.WriteLine("Volume after adding boxes:{0}", box1 + box2);<br>
}<br>
    }<br>
    }<br><br>
OUTPUT:<br>
![image](https://user-images.githubusercontent.com/98145023/152297160-8c6bbef9-e163-47bc-b79c-ba1bcc88c276.png)<br><br>


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

<br><br><br><br>
3)
using System;<br>
namespace Exercises<br>
{<br>
    class PersonalDetails<br>
    {<br>
        string name;<br>
        int age;<br>
        string gender;<br>
        public PersonalDetails(string name, int age, string gender)<br>
        {<br>
            this.name = name;<br>
            this.age = age;<br>
            this.gender = gender;<br>
        }<br>
        public virtual void Display()<br>
        {<br>
            Console.WriteLine("\n-----PERSONAL DETAILS-----\n");<br>
            Console.WriteLine("Name      :" + name);<br>
            Console.WriteLine("Age      :" + age);<br>
            Console.WriteLine("Gender      :" + gender);<br>
        }<br>
        }<br>
    class CourseDetails : PersonalDetails<br>
    {<br>
        int regNo;<br>
        string course;<br>
        int semester;<br>
        public CourseDetails(string name, int age, string gender, int regNo, string course, int semester) : base(name, age, gender)<br>
        {<br>
            this.regNo = regNo;<br>
            this.course = course;<br>
            this.semester = semester;<br>
        }<br>
        public override void Display()<br>
        {<br>
            base.Display();<br>
            Console.WriteLine("\n-----COURSE DETAILS------\n");<br>
            Console.WriteLine("Register Number   :" + regNo);<br>
            Console.WriteLine("Course   :" + course);<br>
            Console.WriteLine("Semester   :" + semester);<br>
        }<br>
    }<br>
    class MarksDetails : CourseDetails<br>
    {<br>
        int[] marks = new int[5];<br>
        int total;<br>
        float average;<br>
        string grade;<br>
        int flagFail;<br>
        public MarksDetails (string name, int age, string gender, int regNo, string course, int semester, int[] marks) : base(name, age, gender, regNo, course, semester)<br>
        {<br>
            total = 0;<br>
            for (int i = 0; i < 5; i++)<br>
            {<br>
                this.marks[i] = marks[i];<br>
                total += marks[i];<br>
                if (marks[i] < 35)<br>
                {<br>
                    flagFail = 1;<br>
                }<br>
            }<br>
            Calculate();<br>
        }<br>
        private void Calculate()<br>
        {<br>
            average = total / 5;<br>
            if (flagFail == 1 || average < 40)<br>
                grade = "Fail";<br>
            else if (average >= 70)<br>
                grade = "Distinction";<br>
            else if (average >= 60)<br>
                grade = "First Class";<br>
            else if (average >= 50)<br>
                grade = "Second Class";<br>
            else<br>
                grade = "Pass Class";<br>
        }<br>
        public override void Display()<br>
        {<br>
            base.Display();<br>
            Console.WriteLine("\n----MARKS DETAILS----\n");<br>
            Console.Write("Marks in 5 subjects:");<br>
            for (int i = 0; i < 5; i++)<br>
                Console.Write(marks[i] + " ");<br>
            Console.WriteLine();<br>
            Console.WriteLine("Total    :" + total);<br>
            Console.WriteLine("Average    :" + average);<br>
            Console.WriteLine("Grade    :" + grade);<br>
        }<br>
    }<br>
class Multilevel<br>
    {<br>
        public static void Main(string []args)<br>
        {<br>
            MarksDetails Student1 = new MarksDetails("Abhijith", 22, "Male", 20190001, "MCA", 5, new int[] { 77, 80, 98, 95, 90 });<br>
            Student1.Display();<br>
        }<br>
}<br>
}<br><br><br>
OUTPUT:<br><br>
![image](https://user-images.githubusercontent.com/98145023/152290300-1ea12047-3257-4d7b-abf6-d63e1a585340.png)<br><br><br>



4)<br><br>

using System;<br>
namespace Exercises<br>
{<br>
    class GrayCodev<br>
    {<br>
        static int getGray(int n)<br>
        {<br>
            return n ^ (n >> 1);<br>
        }<br>
        static void Main(string[] args)<br>
        {<br>
            int InputNum, GrayNum;<br>
            Console.Write("\n Enter the decimal number: ");<br>
            InputNum = Convert.ToInt32(Console.ReadLine());<br>
            Console.WriteLine("\n Binary equivalent of {0}:{1}", InputNum, Convert.ToString(InputNum, 2));<br>
            GrayNum = getGray(InputNum);<br>
            Console.WriteLine("\n Gray Code equivalent of {0}:{1}", InputNum, Convert.ToString(GrayNum,2));<br>
        }<br>
}<br>
    }<br>

OUTPUT:<br><br>
![image](https://user-images.githubusercontent.com/98145023/152293680-54395c6a-3453-417e-b73e-e1d3e37958ea.png)




