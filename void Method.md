# void Method 
###### tags: `method` `concat` `static`
``` csharp
using System;

namespace ConsoleApp2
{
    class Program
    {
        static void Main(string[] args)
        {
            string iTextForIt;
            WriteSomeThing();//使用WriteSomeThing方法輸出 "I am called from a methed"
            Console.WriteLine("Write Something :");
            iTextForIt =Console.ReadLine();
            WriteSomethingSpectific("Yo you Write",iTextForIt);//使用WriteSomethingSpectific方法輸出文字
            Console.Read();
        }

        public static  void WriteSomeThing()//若不加入static ，Main方法則無法訪問，因為Main方法本身也含有static
        {
            Console.WriteLine(  "I am called from a methed");
        }
        public static void WriteSomethingSpectific(string someWord, string myText)
        {
            string combine = string.Concat(someWord, " ", myText);//concat兩個字串達到連接的效果
            Console.WriteLine(combine);//將兩者連接的字串輸出
        }
    }
}
```