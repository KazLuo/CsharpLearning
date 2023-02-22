# static & 實例化

###### tags: `Common`

``` csharp
using System;

namespace ConsoleApp2
{
    class Program
    {
        int age = 15;
        static void Main(string[] args)
        {


            //Console.WriteLine(age);
            //若直接呼叫age則會出現錯誤，原因為非靜態
            //(static)，可在age加上static解決

            //或是使用以下實例化方法解決
            var program = new Program();

            Console.WriteLine(program.age);
            Console.Read();

            

        }
    }
}
```