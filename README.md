# .NET<br><br>

1)C# program to print a Binary Triangle<br>
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






2)C# program to check whether the entered number is an amicable number or not<br><br>
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




3)C# program to illustrate multilevel inheritance with virtual methods(displaying student details)<br><br>
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






4)C# program to craete a gray code<br><br>

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





5)C# program to calculate volume of 2 boxes and find the resultant volume after addition of 2 boxes by impementing operator overloading<br><br>
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


6)C# program to implement priciples of delegates(converting input string to uppercase first,last and entire string)<br><br>
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





7)C# program to generate register number automatially for 100 students using static constructor<br><br>
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



8)C# program to find the frequency of the word "is" in a given sentence<br><br>
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

        
    
9)C# program that benchmarks 2D,jagged array allocation<br><br>
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



10)C# progarm to find the sum of the value on diagonal of the matrix<br><br>
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


    
11)C# progarm to create a file,check the existence of a file and read the contents of the file<br>
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




12)C# progarm to perform file comparison<br><br>
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
}<br><br>
OUTPUT:<br>
![image](https://user-images.githubusercontent.com/98145023/154413241-e1be7210-7b81-42f5-803f-260f9b2ebd08.png)<br>
![image](https://user-images.githubusercontent.com/98145023/154413556-74928336-4601-4601-887b-fd2a528a72e7.png)<br><br><br>


13)C# progarm to implement IComaparable interface<br><br>
using System;<br>
namespace Exercises<br>
{<br>
    class Fraction:IComparable<br>
    {<br>
        int z,n;<br>
            public Fraction(int z,int n)<br>
        {<br>
            this.z = z;<br>
            this.n = n;<br>
        }<br>
        public static Fraction operator+(Fraction a,Fraction b)<br>
        {<br>
            return new Fraction(a.z * b.n + a.n * b.z, a.n * b.n);<br>
        }<br>
        public int CompareTo(Object obj)<br>
        {<br>
            Fraction f = (Fraction)obj;<br>
            if ((float)z / n < (float)f.z / f.n)<br>
                return -1;<br>
            else if ((float)z / n > (float)f.z / f.n)<br>
                return 1;<br>
            else<br>
                return 0;<br>
        }<br>
        public override string ToString()<br>
        {<br>
            return z + "/" + n;<br>
            }<br>
        }<br>
   class ICompInterface<br>
{<br>
    public static void Main()<br>
    {<br>
        Fraction[] a = <br>
            {<br>
            new Fraction (5,2),<br>
            new Fraction (29,6),<br>
            new Fraction (4,5),<br>
            new Fraction (10,8),<br>
            new Fraction (34,7)<br>
            };<br>
        Array.Sort(a);<br>
        Console.WriteLine("Implementing the IComaparable Interface in " + " Displaying Fractions:");<br>
        foreach( Fraction f in a)<br>
        {<br>
            Console.WriteLine(f + " ");<br>
        }<br>
        Console.WriteLine();<br>
        Console.ReadLine();<br>
    }<br>
}<br>
}<br>

OUTPUT:<br>
![image](https://user-images.githubusercontent.com/98145023/154418045-302bafb1-62ab-48e0-b6c4-fc79b3b158b2.png)<br><br>
<br>


14)C# progarm to create thread pools<br><br>
using System;<br>
using System.Threading;<br>
namespace Exercises<br>
{<br>
    class ThreadPoolProg<br>
    {<br>
        public void ThreadFun1(object obj)<br>
        {<br>
            int loop = 0;<br>
            for(loop=0; loop<=4; loop++)<br>
            {<br>
                Console.WriteLine("Thread1 is executing");<br>
            }<br>
        }<br>
         public void ThreadFun2(object obj)<br>
        {<br>
            int loop = 0;<br>
            for (loop = 0; loop <= 4; loop++)<br>
            {<br>
                Console.WriteLine("Thread2 is executing");<br>
            }<br>
        }<br>
        public static void Main()<br>
        {<br>
            ThreadPoolProg TP = new ThreadPoolProg();<br>
        for(int i=0;i<2;i++)<br>
            {<br>
                ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun1));<br>
                ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun2));<br>
            }<br>
            Console.ReadKey();<br>
        }<br>
    }<br>
}<br><br>
OUTPUT:<br>
![image](https://user-images.githubusercontent.com/98145023/154420655-1553be61-c4f8-4d29-9e4e-7fcfa88c1ce8.png)
<br><br><br>



15)C# progarm to demonstrate error handling using try,catch and finally block.<br><br>
using System;<br>
namespace Exercises<br>
{<br>
    class ExceptionHandling<br>
    {<br>
        static void Main(String[] args)<br>
        {<br>
            Age a = new Age();<br>
          try<br>
        {<br>
                a.displayAge();<br>
            }<br>
            catch (AgeIsNegativeException e)<br>
            {<br>
                Console.WriteLine("AgeIsNegativeException:{0}", e.Message);<br>
            }<br>
            finally<br>
            {<br>
                Console.WriteLine("Execution of finally block is done");<br>
            }<br>
        }<br>
    }<br>
}<br>
public class AgeIsNegativeException : Exception<br>
{<br>
    public AgeIsNegativeException(string message):base (message)<br>
    { <br>
}<br>
}<br>
public class AgeV
{<br>
    int age = -5;<br>
    public void displayAge()<br>
    {<br>
        if (age < 0)<br>
        {<br>
            throw (new AgeIsNegativeException("Age cannot be negative"));<br>
        }<br>
        else<br>
        {<br>
            Console.WriteLine("Age is:{0}", age);<br>
        }<br>
    }<br>
}<br><br>
OUTPUT:<br>
![image](https://user-images.githubusercontent.com/98145023/154423674-f541253e-4c27-40e0-9c7a-81efbdb09c38.png)<br><br><br><br>


16)Write a c# program to print fibonacci series without using recursion and using recursion.<br>
using System;<br>
public class FibonacciExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n1 = 0, n2 = 1, n3, i, number;<br>
        Console.Write("Enter the number of elements: ");<br>
        number = int.Parse(Console.ReadLine());<br>
        Console.Write(n1 + " " + n2 + " ");<br>
        for (i = 2; i < number; ++i)<br>  
        {<br>
            n3 = n1 + n2;<br>
            Console.Write(n3 + " ");<br>
            n1 = n2;<br>
            n2 = n3;<br>
        }<br>
    }<br>
}<br>
OUTPUT:<br>
![image](https://user-images.githubusercontent.com/98145023/155659198-60a94015-c6e5-4c86-a9ca-cbee0c856e62.png)<br><br><br>


Write a c# program to check prime number.<br>
using System;<br>
public class PrimeNumberExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n, i, m = 0, flag = 0;<br>
        Console.Write("Enter the Number to check Prime: ");<br>
        n = int.Parse(Console.ReadLine());<br>
        m = n / 2;<br>
        for (i = 2; i <= m; i++)<br>
        {<br>
            if (n % i == 0)<br>
            {<br>
                Console.Write("Number is not Prime.");<br>
                flag = 1;<br>
                break;<br>
            }<br>
        }<br>
        if (flag == 0)<br>
            Console.Write("Number is Prime.");<br>
    }<br>
}<br>
Outout:<br>
![image](https://user-images.githubusercontent.com/98145023/155660647-0a68d7d0-03ed-4c95-aaa5-a41670619a02.png)<br>
![image](https://user-images.githubusercontent.com/98145023/155660763-a7a4539e-17c4-453d-afca-9c81ef5fb82a.png)<br><br>
<br>


Write a c# program to check palindrome number.<br>
using System;<br>
public class PalindromeExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n, r, sum = 0, temp;<br>
        Console.Write("Enter the Number: ");<br>
        n = int.Parse(Console.ReadLine());<br>
        temp = n;<br>
        while (n > 0)<br>
        {<br>
            r = n % 10;<br>
            sum = (sum * 10) + r;<br>
            n = n / 10;<br>
        }<br>
        if (temp == sum)
            Console.Write("Number is Palindrome.");<br>
        else<br>
            Console.Write("Number is not Palindrome");<br>
    }<br>
}<br>
OUTPUT:<br>
![image](https://user-images.githubusercontent.com/98145023/155661751-9860bd02-50e1-449e-a78d-c1acc7aad6c7.png)<br>
![image](https://user-images.githubusercontent.com/98145023/155661998-5100bad7-e8a4-4581-ab9a-324905bd73bb.png)<br><br><br>


Write a c# program to print factorial of a number.<br>
using System;  <br>
  public class FactorialExample  <br>
   {  <br>
     public static void Main(string[] args)  <br>
      {   <br>
       int i,fact=1,number;       <br>
       Console.Write("Enter any Number: ");  <br>     
       number= int.Parse(Console.ReadLine());  <br>    
       for(i=1;i<=number;i++) <br>
      { <br>
        fact=fact*i;  <br>     
       }       <br>
       Console.Write("Factorial of " +number+" is: "+fact);  <br>   
     }  <br> 
  }   <br>
  OUTPUT: <br>
  ![image](https://user-images.githubusercontent.com/98145023/155664450-96b85dfa-d1c2-463f-9436-14c111aad83b.png)<br><br><br>



Write a c# program to check armstrong number.<br>
using System;  <br>
  public class ArmstrongExample  <br>
   {  <br>
     public static void Main(string[] args)  <br>
      {  <br>
       int  n,r,sum=0,temp;  <br>    
       Console.Write("Enter the Number= ");      <br>
       n= int.Parse(Console.ReadLine()); <br>    
       temp=n;      <br>
       while(n>0)      <br>
       {      <br>
        r=n%10;     <br> 
        sum=sum+(r*r*r);      <br>
        n=n/10;      <br>
       }      <br>
       if(temp==sum)      <br>
        Console.Write("Armstrong Number.");    <br>  
       else     <br> 
        Console.Write("Not Armstrong Number.");   <br>   
      }  <br>
  }  <br>
  OUTPUT:<br>
  ![image](https://user-images.githubusercontent.com/98145023/155665985-6daa6d8e-59b6-4ba1-89e2-e4a4976d67a0.png)<br>
  ![image](https://user-images.githubusercontent.com/98145023/155666215-0871e9b9-77fa-4a5d-9886-71f77ae2a326.png)<br><br><br>


Write a c# program to print sum of digits.<br>
using System;  <br>
  public class SumExample  <br>
   {  <br>
     public static void Main(string[] args)  <br>
      {  <br>
       int  n,sum=0,m;<br>         
       Console.Write("Enter a number: ");      <br>
       n= int.Parse(Console.ReadLine()); <br>    
       while(n>0)     <br> 
       {      <br>
        m=n%10;     <br> 
        sum=sum+m;   <br>   
        n=n/10;   <br>   
       }      <br>
       Console.Write("Sum is= "+sum);  <br>     
     }  <br>
  }  <br>
  OUTPUT:<br>
  ![image](https://user-images.githubusercontent.com/98145023/155667166-9820b26a-0c80-4b2a-ae7a-3b66a11dda2b.png)
<br><br><br>



Write a c# program to reverse given number.<br>
using System;<br>
public class ReverseExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n, reverse = 0, rem;<br>
        Console.Write("Enter a number: ");<br>
        n = int.Parse(Console.ReadLine());<br>
        while (n != 0)<br>
        {<br>
            rem = n % 10;<br>
            reverse = reverse * 10 + rem;<br>
            n /= 10;<br>
        }<br>
        Console.Write("Reversed Number: " + reverse);<br>
    }<br>
}<br>
OUTPUT:<br>
![image](https://user-images.githubusercontent.com/98145023/155668217-8eceeaf9-474c-40fb-878a-5a6207fdacf2.png)<br>
<br><br><br>


 C# example to swap two numbers without using third variable.
using System;<br>
  public class SwapExample<br>  
   {  <br>
     public static void Main(string[] args)<br>  
      {<br>  
       int  a=5, b=10;<br>            
       Console.WriteLine("Before swap a= "+a+" b= "+b);<br>    
       a=a*b; //a=50 (5*10)<br>      
       b=a/b; //b=5 (50/10)<br>      
       a=a/b; //a=10 (50/5) <br>   
       Console.Write("After swap a= "+a+" b= "+b); <br>      
     }<br>  
     }<br>
     OUTPUT:<br>
     ![image](https://user-images.githubusercontent.com/98145023/156510041-79d9f844-3cdb-4d5e-be23-890ec1bc42ff.png)<br><br><br>
     
     
     **WINDOWS FORM**<br>
   C# Program to Convert Digits to Words.<br>
   using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>
namespace WindowsFormsApp2<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
        }<br>

        private void button1_Click(object sender, EventArgs e)<br>
        {<br>
            label1.Text = NumtoWord(long.Parse(textBox1.Text));<br>
            label1.Visible = true;<br>
            }<br>
        public string NumtoWord(long number)<br>
        {<br>
            string word = "";<br>
            if (number == 0)<br>
            {<br>
                return "Zero";<br>
            }<br>
            if (number < 0)<br>
            {<br>
                return "Minus" + Math.Abs(number);<br>
            }<br>
            if (number / 100000000)<br>
            {<br>
                word += NumtoWord(number / 10000000) + "Crore";<br>
                number %= 10000000;<br>
            }<br>
            if (number / 100000 > 0)<br>
            {<br>
                word += NumtoWord(number / 100000) + "Lakhs";<br>
                number %= 100000;<br>
            }<br>
            if (number / 1000 > 0)<br>
            {<br>
                word += NumtoWord(number / 1000) + "Thousand";<br>
                number %= 1000;<br>
            }<br>
            if (number / 100 > 0)<br>
            {<br>
                word += NumtoWord(number / 100) + "Hundred";<br>
                number %= 100;<br>
            }<br>
            if (number > 0)<br>
            {<br>
                string[] units = new string[] { "Zero", "One", "Two", "Three", "Four", "Five", "Six",
"Seven", "Eight", "Nine","TEN", "Eleven", "Twelve", "Thirteen", "Fourteen", "Fifteen", "Sixteen",
"Seventeen", "Eighteen", "Nineteen" };<br>
                string[] Tens = new string[] { "Zero", "Ten", "Twenty", "Thirty", "Fourty", "Fifty",
"Sixty", "Seventy", "Eighty", "Ninety" };<br>
                if (number < 20)<br>
                {<br>
                    word += units[number];<br>
                }<br>
                else<br>
                {<br>
                    word += Tens[number / 10];<br>
                    if (number % 10 > 0)<br>
                    {<br>
                        word += units[number % 10];<br>
                    }<br>
                }<br>
            }<br>
            return word;<br>
        }<br>
    }<br>
}<br>
OUTPUT:<br>
![image](https://user-images.githubusercontent.com/98145023/157814187-79a2d650-7ad2-404b-8bff-860507894126.png)<br><br><br>


C# Program to Perform Reversal, Padding and Trimming Operations on string<br>
using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>
namespace WindowsFormsApp5<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
        }<br>
        private void button1_Click(object sender, EventArgs e)<br>
        {<br>
          string inputString, revstr = "";<br>
                int Length;<br>
                inputString = textBox1.Text;<br>
                Length = inputString.Length - 1;<br>
                while (Length >= 0)<br>
                {<br>
                    revstr = revstr + inputString[Length];<br>
                    Length--;<br>
                }<br>
                MessageBox.Show("Reverse String Is : " + revstr, "Result");<br>
            }<br>
private void button2_Click(object sender, EventArgs e)<br>
        {<br>
            string inputString;<br>
            inputString = textBox1.Text;<br>
            MessageBox.Show("The String After Trimming : " + inputString.Trim(), "Result");<br>
        }<br>
        private void button3_Click(object sender, EventArgs e)<br>
        {<br>
                string inputString;<br>
                inputString = textBox1.Text;<br>
                inputString = inputString.PadLeft(5, '*');<br>
                inputString = inputString.PadRight(5, '*');<br>
                MessageBox.Show("String After Padding : " + inputString, "Result");<br>
            }<br>
        }<br>
    }<br>
    OUTPUT:<br>
    ![image](https://user-images.githubusercontent.com/98145023/158752451-cc9e01da-735e-486c-8b67-543ff8311cca.png)<br><br><br>

    
C# Program to Create a Progress Bar Control.<br>
using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading;<br>
using System.Windows.Forms;<br>
namespace WindowsFormsApp6<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
        }<br>
        private void Form1_Load(object sender, EventArgs e)<br>
        {<br>
            backgroundWorker1.WorkerReportsProgress = true;<br>
            backgroundWorker1.RunWorkerAsync();<br>
        }<br>
        private void backgroundWorker1_DoWork(object sender, DoWorkEventArgs e)<br>
        {<br>
            for (int i = 1; i <= 100; i++)<br>
            {<br>
                Thread.Sleep(50);<br>
                backgroundWorker1.ReportProgress(i);<br>
            }<br>
        }<br>
private void backgroundWorker1_ProgressChanged(object sender, ProgressChangedEventArgs e)<br>
        {<br>
            progressBar1.Value = e.ProgressPercentage;<br>
            this.Text = "Progress: " + e.ProgressPercentage.ToString() + "%";<br>
        }<br>
    }<br>
}<br>
OUTPUT:<br>
![image](https://user-images.githubusercontent.com/98145023/158753271-b9aac8c0-e5ee-49f8-ad24-6e311499744a.png)<br><br><br>


 Develop a winform application to create flat clock.<br>
 using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>
namespace WindowsFormsApp7<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
        }<br>
private void Form1_Load(object sender, EventArgs e)<br>
        {<br>
            System.Timers.Timer timer = new System.Timers.Timer();<br>
            timer.Interval = 1000;//1s<br>
            timer.Elapsed += Timer_Elapsed;<br>
            timer.Start();<br>
        }<br>
        private void Timer_Elapsed(object sender, System.Timers.ElapsedEventArgs e)<br>
        {<br>
            circularProgressBar1.Invoke((MethodInvoker)delegate<br>
            {<br>
                circularProgressBar1.Text = DateTime.Now.ToString("hh:mm:ss");<br>
                circularProgressBar1.SubscriptText = DateTime.Now.ToString("tt");//AM or PM<br>
            });<br>
        }<br>
        }<br>
}<br>
OUTPUT:<br>
![image](https://user-images.githubusercontent.com/98145023/158941954-d1c19a9d-8760-4dfa-b174-1a0a7220262e.png)
<br><br><br>



C# Program to perform a number guessing game.<br>
using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

namespace WindowsFormsApp10<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        static Random r = new Random();<br>
        int value;<br>
        int guessnum;<br>
        int win = 10;<br>
        int guess = 1;<br>
        Button button1;<br>
        TextBox textBox1;<br>
        RichTextBox richTextBox1;<br>
        RichTextBox richTextBox2;<br>
        Label label4;<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
            value = r.Next(10);<br>
            this.Controls.Clear();<br>
            this.BackColor = Color.SkyBlue;<br>
            this.AutoSize = true;<br>
            this.Padding = new Padding(16);<br>
            Label label = new Label();<br>
            label.Text = "Pick a number between 1 and 10";<br>
            label.Bounds = new Rectangle(10, 20, 340, 40);<br>
            label.Font = new Font("Arial", 16);<br>
            textBox1 = new TextBox();<br>
            textBox1.Bounds = new Rectangle(20, 50, 120, 80);<br>
            textBox1.Font = new Font("Arial", 24);<br>
            button1 = new Button();<br>
            button1.Text = " Check Your Guess ";<br>
            button1.Bounds = new Rectangle(160, 50, 120, 40);<br>
            button1.BackColor = Color.LightGray;<br>
            button1.Click += new EventHandler(button1_Click);<br>
            Label label2 = new Label();<br>
            label2.Text = "Low Guess";<br>
            label2.Bounds = new Rectangle(20, 150, 160, 40);<br>
            label2.Font = new Font("Arial", 18);<br>
            richTextBox1 = new RichTextBox();<br>
            richTextBox1.Bounds = new Rectangle(20, 190, 160, 300);<br>
            richTextBox1.Font = new Font("Arial", 16);<br>
            Label label3 = new Label();<br>
            label3.Text = "High Guess";<br>
            label3.Bounds = new Rectangle(180, 150, 160, 40);<br>
            label3.Font = new Font("Arial", 18);<br><br>
            richTextBox2 = new RichTextBox();<br>
            richTextBox2.Bounds = new Rectangle(180, 190, 160, 300);<br>
            richTextBox2.Font = new Font("Arial", 16);<br>
            label4 = new Label();<br>
            label4.Bounds = new Rectangle(20, 100, 340, 40);<br>
            label4.Font = new Font("Arial", 16);<br>
            this.Controls.Add(label);<br>
            this.Controls.Add(textBox1);<br>
            this.Controls.Add(button1);<br>
            this.Controls.Add(label4);<br><br>
            this.Controls.Add(label2);<br>
            this.Controls.Add(label3);<br>
            this.Controls.Add(richTextBox1);<br>
            this.Controls.Add(richTextBox2);<br>
        }<br>
        private void button1_Click(object sender, EventArgs e)<br><br>
        {<br>
            // Coding of game <br>
            if (textBox1.Text == "")<br>
            {<br>
                return;<br>
            }<br>
            guessnum = Convert.ToInt32(textBox1.Text);<br>
            textBox1.Text = String.Empty;<br>
            if (win >= 0)<br>
            {<br>
                if (guessnum == value)<br>
                {<br>
                    MessageBox.Show("You have guessed the number! \n The number was " + value);<br>
                    InitializeComponent();<br>
                }<br>
                else if (guessnum < value)<br>
                {<br>
                    richTextBox1.Text += guessnum + "\n";<br>
                    MessageBox.Show("wrong Guess and number of guesses left are  " + (10 - guess));<br>
                    }<br>
                else if (guessnum > value)<br>
                {<br>
                    richTextBox2.Text += guessnum + "\n";<br>
                    MessageBox.Show("wrong Guess and number of guesses left are  " + (10 - guess));<br>
                }<br>
                guess++;<br>
                win--;<br>
            }<br>
            if (guess == 11)<br>
            {<br>
                label4.Text = "You loose,Correct Guess is " + value;<br>
            }<br>
        }<br>
    }<br>
}<br>
OUTPUT:<br>
![image](https://user-images.githubusercontent.com/98145023/159849191-a44563f3-b41e-488f-a071-5baa95084ff0.png)<br><br><br>



Develop an application to create a notepad.<br>
using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

namespace notepad   <br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        private string fileName;<br>
        private RichTextBox txtContent;<br>
        private ToolBar toolBar;<br>
        internal Form1()<br>
        {<br>
            fileName = null;<br>
            InitializeComponents();<br>
        }<br>
        void InitializeComponents()<br>
        {<br>
            this.Text = "My notepad";<br>
            this.MinimumSize = new Size(600, 450);<br>
            this.FormClosing += new FormClosingEventHandler(NotepadClosing);<br>
            this.MaximizeBox = true;<br>
            toolBar = new ToolBar();<br>
            toolBar.Font = new Font("Arial", 16);<br>
            toolBar.Padding = new Padding(4);<br>
            toolBar.ButtonClick += new ToolBarButtonClickEventHandler(toolBarClicked);<br>
            ToolBarButton toolBarButton1 = new ToolBarButton();<br>
            ToolBarButton toolBarButton2 = new ToolBarButton();<br>
            ToolBarButton toolBarButton3 = new ToolBarButton();<br>
            toolBarButton1.Text = "New";<br><br>
            toolBarButton2.Text = "Open";<br>
            toolBarButton3.Text = "Save";<br>
            toolBar.Buttons.Add(toolBarButton1);<br>
            toolBar.Buttons.Add(toolBarButton2);<br>
            toolBar.Buttons.Add(toolBarButton3);<br>
            txtContent = new RichTextBox();<br>
            txtContent.Size = this.ClientSize;<br>
            txtContent.Height -= toolBar.Height;<br>
            txtContent.Top = toolBar.Height;<br>
            txtContent.Anchor = AnchorStyles.Left | AnchorStyles.Right |<br>
           AnchorStyles.Top | AnchorStyles.Bottom;<br>
            txtContent.Font = new Font("Arial", 16);<br>
            txtContent.AcceptsTab = true;<br>
            txtContent.Padding = new Padding(8);<br>

            this.Controls.Add(toolBar);<br>
            this.Controls.Add(txtContent);<br>
        }<br>
        private void toolBarClicked(Object sender, ToolBarButtonClickEventArgs e)<br>
        {<br>
            saveFile();<br>
            switch (toolBar.Buttons.IndexOf(e.Button))<br>
            {<br>
                case 0:<br>
                    this.Text += "My notepad";<br>
                    txtContent.Text = string.Empty;<br>
                    fileName = null;<br>
                    break;<br>
                case 1:<br>
                    OpenFileDialog openDlg = new OpenFileDialog();<br>
                    if (DialogResult.OK == openDlg.ShowDialog())<br>
                    {<br>
                        fileName = openDlg.FileName;<br>
                        txtContent.LoadFile(fileName);<br>
                        this.Text = "My notepad " + fileName;<br>
                    }<br>
                    break;<br>
            }<br>
        }<br>
        void saveFile()<br>
        {<br>
            if (fileName == null)<br>
            {<br>
                SaveFileDialog saveDlg = new SaveFileDialog();<br>
                if (DialogResult.OK == saveDlg.ShowDialog())<br>
                {<br>
                    fileName = saveDlg.FileName;<br>
                    this.Text += " " + fileName;<br>
                }<br>
            }<br>
            else<br>
            {<br>
                txtContent.SaveFile(fileName, RichTextBoxStreamType.RichText);<br>
            }<br>
        }<br>
        private void NotepadClosing(Object sender, FormClosingEventArgs e)<br>
        {<br>
            saveFile();<br>
        }<br>
        static void main(String[] args)<br>
        {<br>
 Application.Run(new Form1());<br>
        }<br>
    }<br>
}<br>
OUTPUT:<br>
![image](https://user-images.githubusercontent.com/98145023/159862390-11318165-b643-4924-a9b1-b8889e487164.png)<br><br><br>
