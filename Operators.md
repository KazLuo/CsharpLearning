# Operators(運算子)

###### tags: `Operators`

```csharp=
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace OperatorsC
{
    class Program
    {
        static void Main(string[] args)
        {
            int num1 = 5;
            int num2 = 3;
            int num3;

            // unary operators 單元運算子
            num3 = -num1;
            Console.WriteLine("num3 is {0}",num3 );//-num1為-5

            bool isSunny = true; //布林
            Console.WriteLine("is it sunny? {0}", !isSunny);//使用"!"為故輸出為False

            // increment operators 加法運算子
            int num = 0;
            num++;// num+1
            Console.WriteLine("num is {0}", num);//顯示+1後的num
            Console.WriteLine("num is {0}", num++);//當下num++不會作用，還是1
            // pre increment
            Console.WriteLine("num is {0}", ++num);//當下++num已作用，包含前面num++總計為3

			// decrement opertor 減法運算子
			num--;//num-1
            Console.WriteLine("num is {0}", num);//顯示num--結果，結果為2
            Console.WriteLine("num is {0}", num--);//當下num--不作用，結果為2
            // pre decrement
            Console.WriteLine("num is {0}", --num);//當下--num已作用，包含面為0

            int result;

            result = num1 + num2;
            Console.WriteLine("result of num1 + num2 is {0}", result);
            result = num1 - num2;
            Console.WriteLine("result of num1 - num2 is {0}", result);
            result = num1 / num2;
            Console.WriteLine("result of num1 / num2 is {0}", result);
            result = num1 * num2;
            Console.WriteLine("result of num1 * num2 is {0}", result);
            result = num1 % num2;
            Console.WriteLine("result of num1 % num2 is {0}", result);

            // relational and type operators
            bool isLower;
            isLower = num1 < num2;
            Console.WriteLine("result of num1 < num2 is {0}", isLower);

            // equality operator
            bool isEqual;
            isEqual = num1 == num2;
            Console.WriteLine("result of num1 == num2 is {0}", isEqual);

            isEqual = num1 != num2;
            Console.WriteLine("result of num1 != num2 is {0}", isEqual);

            // conditional operators
            bool isLowerAndSunny;
            // condition1 AND condition2
            isLowerAndSunny = isLower && isSunny;//And運算子， isLower為False isSunny為True 結果為False
            Console.WriteLine("result of isLower && isSunny is {0}", isLowerAndSunny);

            // condition1 OR condition2
            isLowerAndSunny = isLower || isSunny; //OR運算子， isLower為False isSunny為True  結果為True
			Console.WriteLine("result of isLower || isSunny is {0}", isLowerAndSunny);
            Console.ReadKey();
        }
    }
}

```