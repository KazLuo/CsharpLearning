#Continue & Break
###### tags: `continue` `break`
```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace DoWhileLoop
{
    class Program
    {
        static void Main(string[] args)
        {
            breakState();
			Console.Write("------------------------------------");
			continueState();
			Console.Read();


		}
        
        static void breakState()//break狀態
        {
			for (int counter = 0; counter < 10; counter++)
			{
				Console.WriteLine(counter);
				if (counter % 2 == 0)
				{
					Console.WriteLine("is an odd");
					break;
				}

			}
		}

		static void continueState()//continue狀態
		{
			for (int counter = 0; counter < 10; counter++)
			{
				
				if (counter % 2 == 0)
				{
					Console.WriteLine("is not an odd");
					continue;
				}
				Console.WriteLine(counter);//記得Console.WriteLine的位置 若在前面則會先顯示數值後才會顯示 "is not an odd"

			}
		}
		
	}
}

```

## 補充
**一開始並不懂continue的作用，畢竟當if條件達成有無continue皆可正常運作，所以查了一些資料**

continue 是 C# 中的一个关键字，用于在循环结构中跳过当前迭代并开始下一次迭代。它通常用于条件语句中，以便在满足某些条件时跳过循环中的某些代码。

虽然 continue 关键字可能不像一些其他关键字（如 if 或 while）那样频繁使用，但在某些情况下，它仍然是很有用的。例如，当需要在循环中跳过某些特定值或条件时，使用 continue 可以让代码更加简洁和可读。

总的来说，虽然 continue 关键字在 C# 中的使用可能不如其他关键字那么普遍，但它仍然是一种非常有用的编程工具，可以帮助简化代码并使其更易于理解。

当使用 continue 关键字时，它会跳过当前迭代并开始下一次迭代。以下是一个使用 continue 的示例代码，它计算一个数组中除了负数以外的所有元素的和：

```csharp
Copy code
int[] numbers = { 1, -2, 3, -4, 5 };
int sum = 0;

foreach (int num in numbers)
{
    if (num < 0)
    {
        // 如果当前数字是负数，跳过当前迭代
        continue;
    }

    // 如果当前数字不是负数，将其添加到总和中
    sum += num;
}

Console.WriteLine($"除了负数以外的所有数字的总和为：{sum}");
```
在上面的示例代码中，当 foreach 循环迭代到 -2 和 -4 时，它会执行 continue 语句并跳过当前迭代。这意味着这些负数不会被包括在总和中。因此，最后输出的结果是：除了负数以外的所有数字的总和为：9。
