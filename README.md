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
<br><br><br><br>





5)<br>
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
    }<br><br><br>
    OUTPUT:<br>
    ![image](https://user-images.githubusercontent.com/98145023/152297844-fb63b288-5094-4980-ad4b-327c662e0cde.png)<br><br><br><br>


6)<br>
using System;<br>
namespace Exercices<br>
{<br>
    class Delegates<br>
    {<br>
        delegate string UppercaseDelegate(string input);<br>
        static string UppercaseFirst(string input)<br>
        {<br>
            char[] buffer = input.ToCharArray();<br>
            buffer[0] = char.ToUpper(buffer[0]);<br>
            return new string(buffer);<br>
        }<br>
        static string UppercaseLast(string input)<br>
        {<br>
            char[] buffer = input.ToCharArray();<br>
            buffer[buffer.Length - 1] = char.ToUpper(buffer[buffer.Length - 1]);<br>
            return new string(buffer);<br>
        }<br>
        static String UppercaseAll(string input)<br>
        {<br>
            return input.ToUpper();<br>
        }<br>
        static void WriteOutput(string input, UppercaseDelegate del)<br>
        {<br>
            Console.WriteLine("Input String:{0}", input);<br>
            Console.WriteLine("Output String:{0}", del(input));<br>
        }<br>
                static void Main()<br>
            {<br>
                WriteOutput("tom", new UppercaseDelegate(UppercaseFirst));<br>
                WriteOutput("tom", new UppercaseDelegate(UppercaseLast));<br>
                WriteOutput("tom", new UppercaseDelegate(UppercaseAll));<br>
                Console.ReadLine();<br>
                }<br>
    }<br>
}<br><br>
OUTPUT:<br>
![Screenshot 2022-02-03 131657](https://user-images.githubusercontent.com/98145023/152474995-f1ec22f3-ce14-41dc-afb7-19acde6c0855.png)<br><br><br><br>





7)<br>
using System;<br>
namespace Exercises<br>
{<br>
    class RegisterNum<br>
    {<br>
        int regNo;<br>
        static int startNum;<br>
        static RegisterNum()<br>
        {<br>
            startNum = 20210000;<br>
        }<br>
        RegisterNum()<br>
        {<br>
            regNo = ++startNum;<br>
        }<br>
        public static void Main(string[] args)<br>
        {<br>
            for (int i = 0; i < 100; i++)<br>
            {<br>
                RegisterNum Student = new RegisterNum();<br>
                Console.WriteLine("Student{0}:{1}", i + 1, Student.regNo);<br>
            }<br>
        }<br>
    }<br>
}<br>
OUTPUT:<br>
![image](https://user-images.githubusercontent.com/98145023/152477165-99f0193f-7fb2-4ceb-bc61-10eada5df8f7.png)<br>
![image](https://user-images.githubusercontent.com/98145023/152477240-75238add-7d11-46ca-a62c-4d4c6dd9e8c8.png)<br>
![image](https://user-images.githubusercontent.com/98145023/152477389-2cfb4c68-3a0d-4ee9-958d-2a1dc959b11c.png)<br>
![image](https://user-images.githubusercontent.com/98145023/152477477-0666d55b-f4c4-4b7c-8dc4-4a3e3ef2fc8a.png)<br><br><br><br>



8)<br>
using System;<br>
namespace Exercises<br>
{<br>
    class FrequencyIS<br>
    {<br>
        static void Main(string[]args)<br>
        {<br>
            int count = 1;<br>
            string inputString;<br>
            Console.WriteLine("\n----Frequency of word 'is'----");<br>
            Console.Write("\n Enter the input string:");<br>
            inputString = Console.ReadLine();<br>
            char[] seperator = { ',', ' ', '.', '!', '\n' };<br>
            string testString = inputString.ToLower();<br>
            String[] outcomes = testString.Split(seperator);<br>
            foreach (String s in outcomes)<br>
            {<br>
                Console.WriteLine(s);<br>
                if (s == "is")<br>
                    count++;<br>
            }<br>
            Console.WriteLine("\n Number of 'is' in '"+inputString+"' is: "+count);<br>
                }<br>
                }<br>
                }<br><br>
                OUTPUT:<br>
                ![image](https://user-images.githubusercontent.com/98145023/152480170-5955da77-d49b-4e48-bb97-ee037ed0bc2b.png)<br><br><br><br>

        
    
9)<br>
using System;<br>
using System.Diagnostics;<br>
namespace Exercises<br>
{<br>
    class  BenchmarkAllocation<br>
    {<br>
        const int _max= 100000;<br>
        static void Main(string[] args)<br>
        {<br>
            var Arr2D = new int[100, 100];<br>
            var ArrJagged = new int[100][];<br>
            for (int i = 0; i < 100; i++)<br>
            {<br>
                ArrJagged[i] = new int[100];<br>
            }<br>
            var Stopwatch2D = Stopwatch.StartNew();<br>
            for (int i = 0; i < _max; i++)<br>
            {<br>
                for (int j = 0; j < 100; j++)<br>
                {<br>
                    for (int k = 0; k < 100; k++)<br>
                    {<br>
                        Arr2D[j, k] = k;<br>
                    }<br>
                }<br>
            }<br>
            Stopwatch2D.Stop();<br>
            var StopwatchJagged = Stopwatch.StartNew();<br>
            for (int i = 0; i < _max; i++)<br>
            {<br>
                for (int j = 0; j < 100; j++)<br>
                {<br>
                    for (int k = 0; k < 100; k++)<br>
                    {<br>
                        ArrJagged[j][k] = k;<br>
                    }<br>
                }<br>
            }<br>
            StopwatchJagged.Stop();<br>
            Console.Write("\n Time taken for allocation in case of 2D array: ");<br>
            Console.WriteLine(Stopwatch2D.Elapsed.TotalMilliseconds+"milliseconds");<br>
            Console.Write("\n Time taken for allocation in case of Jagged array: ");<br>
            Console.WriteLine(StopwatchJagged.Elapsed.TotalMilliseconds + "milliseconds");<br>
        }<br>
    }<br>
}<br><br>
OUTPUT:<br>
![image](https://user-images.githubusercontent.com/98145023/152481741-9f85af5d-f21a-4d83-b24f-7099a43c1b0f.png)<br><br><br>
<br>
<br>



10)<br>
using System;<br>
namespace Exercises<br>
{<br>
    class SumOfDiagonals<br>
        {<br>
    static void Main(string[] args)<br>
    {<br>
        int MaxRow, MaxCol, Sum = 0;<br>
        int[,] Matrix;<br>
        Console.WriteLine("\n-----SUM OF DIAGONAL OF A MATRIX-----\n");<br>
        Console.Write("\n Enter the number of rows:");<br>
        MaxRow = Convert.ToInt32(Console.ReadLine());<br>
        Console.Write("\n Enter the number of COLUMNS:");<br>
        MaxCol = Convert.ToInt32(Console.ReadLine());<br>
        if (MaxRow != MaxCol)<br>
        {<br>
            Console.WriteLine("\n The Dimensions entered are not of Suare Matrix.");<br>
            Console.WriteLine("\n Existing the program..");<br>
            return;<br>
        }<br>
        Matrix = new int[MaxRow, MaxCol];<br>
        for (int i = 0; i < MaxRow; i++)<br>
        {<br>
            for (int j = 0; j < MaxCol; j++)<br>
            {<br>
                Console.Write("\n Enter the ({0},{1})th element of the matrix :", (i + 1), (j + 1));<br>
                Matrix[i, j] = Convert.ToInt32(Console.ReadLine());<br>
            }<br>
        }<br>
    Console.WriteLine("\n The entered matrix is :");<br>
for (int i = 0; i<MaxRow;i++)<br>
        {<br>
            for(int j=0;j<MaxCol;j++)<br>
            {<br>
        Console.Write("   "+Matrix[i, j]);<br>
                if(i==j)<br>
                {<br>
                    Sum += Matrix[i, j];<br>
                }<br>
        }<br>
                Console.WriteLine();<br>
}<br>
Console.WriteLine("\n The Sum of Diagonal is "+Sum);<br>
}<br>
}<br>
}<br><br>
OUTPUT:<br>
![image](https://user-images.githubusercontent.com/98145023/152485524-dea27302-a89b-4bbe-a796-c3aa8349364d.png)<br>
![image](https://user-images.githubusercontent.com/98145023/152485604-a08eff02-3371-4595-aa98-f6c5cf17deba.png)<br><br><br><br>


    
11)<br>
using System;<br>
  using System.IO;<br>
namespace Exercises<br>
{<br>
    class FileRead<br>
    {<br>
        public static void Main()<br>
        {<br>
            string fileName;<br>
            while (true)<br>
            {<br>
                Console.WriteLine("\n------MENU--------\n");<br>
                Console.WriteLine("\n 1.Create a File");<br>
                Console.WriteLine("\n 2.Existence of the file");<br>
                Console.WriteLine("\n 3.Read the contents of the file");<br>
                Console.WriteLine("\n 4.Exit");<br>
                Console.Write("\n Enter your choice :");<br>
                int ch = int.Parse(Console.ReadLine());<br>
                switch (ch)<br>
                {<br>
                    case 1:<br>
                        Console.Write("\n Enter the file name to create: ");<br>
                        fileName = Console.ReadLine();<br>
                        Console.WriteLine("\n Write the ocntents to the file: \n");<br>
                        string r = Console.ReadLine();<br>
                        using (StreamWriter fileStr = File.CreateText(fileName))<br>
                            {<br>
                            fileStr.WriteLine(r);<br>
                        }<br>
                        Console.WriteLine("File is created...");<br>
                    case 2:<br>
                        Console.Write("\n Enter the file name: ");<br>
                        fileName = Console.ReadLine();<br>
                        if (File.Exists(fileName))<br>
                        {<br>
                            Console.WriteLine("File exists...");<br>
                        }<br>
                        else<br>
                        {<br>
                            Console.WriteLine("File does not exist in the current directory!");<br>
                        }<br>
                        break;<br>
                    case 3:<br>
                        Console.Write("\n Enter the file name to read the contents: \n");<br>
                        fileName = Console.ReadLine();<br>
                        if (File.Exists(fileName))<br>
                        {<br>
                            using (StreamReader sr = File.OpenText(fileName))<br>
                            {<br>
                                string s = "";<br>
                                Console.WriteLine("Here is the content of the file:");<br>
                                while ((s =sr.ReadLine()) != null)<br>
                                    {<br>
                                    Console.WriteLine(s);<br>
                                }<br>
                                Console.WriteLine("");<br>
                            }<br>
                        }<br>
                        else<br>
                        {<br>
                            Console.WriteLine("File does not exists");<br>
                        }<br>
                        break;<br>
                    case 4:<br>
                        Console.WriteLine("\n Exiting...");<br>
                        return;<br>
                    default:<br>
                        Console.WriteLine("\n Invalid Choice.");<br>
                        break;<br>
                }<br>
}<br>
        }<br>
    }<br>
}<br><br>
OUTPUT:<br>
![image](https://user-images.githubusercontent.com/98145023/152489502-a0b27fb3-9232-4cad-8347-ea3f5686227b.png)
<br>
![image](https://user-images.githubusercontent.com/98145023/152489652-8e5d36cd-68d6-45b2-85b2-7e74e8a9a5f2.png)
<br>
![image](https://user-images.githubusercontent.com/98145023/152489716-15f9d102-4d97-4da1-a316-85ec74e5ccfe.png)
<br>
![image](https://user-images.githubusercontent.com/98145023/152489774-1abc66a8-d288-4ebf-bb46-e26bf120052b.png)
<br><br><br>




12)<br>
using System;<br>
using System.IO;<br>
namespace Exercises<br>
{<br>
    class FileRead<br>
    {<br>
        public static void Main()<br>
        {<br>
            string file1;<br>
            string file2;<br>
            Console.Write("Enter the first file path:");<br>
            file1 = Console.ReadLine();<br>
            Console.Write("Enter the second file path:");<br>
            file2 = Console.ReadLine();<br>
            if (!File.Exists(file1))<br>
            {<br>
                Console.WriteLine("First file does not exist!");<br>
            }<br>
            else if (!File.Exists(file2))<br>
            {<br>
                Console.WriteLine("Second file does not exist!");<br>
            }<br>
            else if (File.ReadAllText(file1) == File.ReadAllText(file2))<br>
            {<br>
                Console.WriteLine("Both files contain the same context");<br>
}<br>
            else<br>
            { <br>
        Console.WriteLine("Contents of files are not same");<br>
    }<br>
}<br>
}<br>
}<br>
OUTPUT:<br><br>
![image](https://user-images.githubusercontent.com/98145023/154413241-e1be7210-7b81-42f5-803f-260f9b2ebd08.png)<br>
![image](https://user-images.githubusercontent.com/98145023/154413556-74928336-4601-4601-887b-fd2a528a72e7.png)<br><br><br>


