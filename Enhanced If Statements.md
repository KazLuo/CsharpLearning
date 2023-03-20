# Enhanced If Statements
###### tags: `if`

```csharp=
// See https://aka.ms/new-console-template for more information
using System;

class Program
{
	static int temperture = 50;
    //注意這邊要使用string，詳細如以下說明
	static string stateOfMatter;

	static void Main(string[] args)
	{
		//一般 if else用法
		/*
		if (temperture <0)
		{
			Console.WriteLine("ice");
		}
		else if (temperture > 0 && temperture <100)
		{
			Console.WriteLine("water");
		}
		else
		{
            Console.WriteLine("Air");
        }
		*/

		//精簡 if else用法
        //a? b:c ? d:e

		stateOfMatter = temperture < 0 ? "ice" : temperture > 0 && temperture < 100 ? "water" : "air";
		//stateOfMatter = 比較temperture 是否 <0 是則"ice"，否則進入下一階段 temperture >0 && <100，是則"water"否則"air"

		Console.WriteLine($"{stateOfMatter}");
    }
}

```

![](https://i.imgur.com/JNA7BHf.png)

ChatGPT
在精簡 if else 用法中， stateOfMatter 的數據類型為 int，但賦值的是字串（string）類型的值。因此，需要將 stateOfMatter 的數據類型改為 string。

以下是修正後的程式碼：

```csharp
Copy code
using System;

class Program
{
    static int temperture = 100;
    static string stateOfMatter;

    static void Main(string[] args)
    {
        stateOfMatter = temperture < 0 ? "ice" : temperture > 0 && temperture < 100 ? "water" : "air";
        Console.WriteLine($"{stateOfMatter}");
    }
}
```
這樣程式就可以正確地編譯和運行。