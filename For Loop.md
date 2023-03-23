#  For Loop

###### tags: `for`

```csharp
// See https://aka.ms/new-console-template for more information
using System;
using System.ComponentModel;
using System.Reflection.Metadata;
using System.Threading.Channels;

class Program
{
	
	static void Main(string[] args)
	{
		for(int i = 0; i < 10; i++)
		{
		
            Console.WriteLine(i);
        }
		//在 C# 的 for 循環中，初始化語句 (i = 0)、判斷條件語句 (i < 10) 和 後置遞增運算子 (i++) 依次執行。
		//因此，for 循環在第一次執行之前會執行初始化語句，即 i = 0，然後進行判斷條件
		//如果判斷條件為真 (i < 10)，則執行循環體內的代碼，即 Console.WriteLine(i)
		//然後執行後置遞增運算子 i++，i 的值增加 1。循環體內的代碼執行完畢之後，再次進行判斷條件
		//以此類推，直到判斷條件為假，for 循環才結束
		//因此，在 for 循環第一次執行之前，初始化語句已經被執行了一次。
	}
}

```
### 執行順序
![](https://i.imgur.com/lm0M9OR.png)
