# Method(return)
###### tags: `method` `return`
```csharp
using System;
namespace Method
{
    class Program
    {

        static void Main(string[] args)
        {
            int resultAdd = Add(Add(3, 4), Add(6, 4));//使用Add方法加總數值
            //方法可作為參數疊加  Method(parameter1,parameter2) ->Method(Method(a,b),Method(c,d))
            double MutiplyAns = Mutiply(3,4);
            outPut(resultAdd.ToString());//使用outPut方法輸出並將值轉換為字串
            outPut(MutiplyAns.ToString());//使用outPut方法輸出並將值轉換為字串
            Console.WriteLine(resultAdd);//輸出resultAdd
            Console.WriteLine(MutiplyAns);//輸出MutiplyAns
            Console.Read();
        }
        public static int Add(int x, int y) //非靜態方法情況下需要return回傳
        {
            return x + y;
        }
        public static double Mutiply(double x, double y)  //非靜態方法情況下需要return回傳
        {
            return x * y;
        }
        public static void outPut(string myText)
        {
           Console.WriteLine(myText);//void 要使用Console來進行回傳，而不是return
        }


    }
}
