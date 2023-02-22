# About String 
###### tags: `String`
``` csharp

using System;

namespace ConsoleApp2
{
    class Program
    {

    static void Main(string[] args)
    {
        string name = Console.ReadLine();//注意string 是一個類別，而不是資料型態(integer/bool)之類的
        string message = "My name is " + name;
        string capsmessage = message.ToUpper();
        string tolowermessage = message.ToLower();

        Console.WriteLine($"請輸入名稱: { name}");
        Console.WriteLine($"{message}");
        Console.WriteLine($"{capsmessage}");
        Console.WriteLine($"{tolowermessage}");


           




        }
    }
```