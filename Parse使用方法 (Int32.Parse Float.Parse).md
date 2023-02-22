# Parse使用方法 (Int32.Parse Float.Parse)

###### tags: `Int32` `Parse` `Float`
``` csharp
using System;

namespace ConsoleApp2
{
    class Program
    {
        static void Main(string[] args)
        {
            string myString = "15";//字串15
            string mySecondString = "12";//字串12
            string result = myString + mySecondString;//兩者相加

            int num1 = Int32.Parse(myString);
            int num2 = Int32.Parse(mySecondString);

            int numPluse = num1 + num2;

            Console.WriteLine(result);//在無parse轉換的情況下輸出為1512
            Console.WriteLine(numPluse);//使用parse將字串轉換為整數(int)輸出為27

       

            //以下為課程挑戰
            
                string stringForFloat = "0.85"; // datatype should be float
                string stringForInt = "12345"; // datatype should be int

            float answer1 = float.Parse(stringForFloat);//使用float.Parse方法轉換string to float
            int answer2 = Int32.Parse(stringForInt);

            Console.WriteLine(answer1);
            Console.WriteLine(answer2);
            Console.Read();



        }
    }
}
```