# C# int/float 顯式轉換 & 隱性轉換 (Implicit conversion & explicit convertion)

###### tags: `Float` `Common` 


``` csharp
using System;

namespace ConsoleApp2
{
    class Program
    {
        static void Main(string[] args)
        {
            //隱性轉換 int -> long
            int num = 12345645;
            long bignum = num;
            //隱性轉換 float -> double
            //切記float 只能隱性轉換double , 其餘皆須用顯式轉換
            float myFloat = 12.37f;
            double myNewdouble = myFloat;
        
            //顯性轉換
            int newInt;
            newInt = (int)myFloat;

            //typeConversion
            string mystring = myNewdouble.ToString();
            string myFloatString = myFloat.ToString();
            bool sunShining = false;
            string myStringBool = sunShining.ToString();

            Console.WriteLine(newInt);
            Console.WriteLine(mystring);
            Console.WriteLine(myFloatString);
            Console.WriteLine(myStringBool);
            Console.Read();
        }
    }
}
```


---

![](https://i.imgur.com/Urhqvgf.png)


---

![](https://i.imgur.com/CaZEMsz.png)





Reference

Microsoft- 內建數值轉換
https://learn.microsoft.com/zh-tw/dotnet/csharp/language-reference/builtin-types/numeric-conversions
Microsoft- 隱性&顯性轉換
https://learn.microsoft.com/zh-tw/dotnet/csharp/programming-guide/types/casting-and-type-conversions