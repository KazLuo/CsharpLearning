# 字串輸出技巧 (String Manipulation)
###### tags: `String`
``` csharp
namespace StringManipulation
{
    class Program
    {

        static void Main(string[] args)
        {
            //字串輸出方法
            string name = "Bob";
            string age = "24";

            //1.直接字串+變數 string contatenation
            Console.WriteLine("Hi,My Name is "+name+", I'm "+age+" years old");

            //2.string formatting(use index)
            Console.WriteLine("Hi,My Name is {0}, I'm {1} years old",name,age);
            //3.string interpolation
            Console.WriteLine($"Hi,My Name is {name}, I'm {age} years old");
            //4.逐字輸出verbatim string(逐字輸出指令會失效適用於路徑檔
            Console.WriteLine(@"Hi,My Name is Bob \n I'm {age} years old");
            //5.\n 換行
            Console.WriteLine("Hi,My Name is Bob \n I'm 24 years old");
            Console.Read();
        }
    }
}
``` 