# Enhanced If Statements (三元運算符)
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



### Practice

```charp=
// See https://aka.ms/new-console-template for more information
using System;
using System.ComponentModel;
using System.Reflection.Metadata;
using System.Threading.Channels;

class Program
{
	

	static void Main(string[] args)
	{
		/*If the input value is not an integer value, it should print to the console "Not a valid Temperature".
		And if the input value is the valid integer then it should work as mentioned below.
		If input temperature value is <= 15 it should write "it is too cold here" to the console.
		If input temperature value is >= 16 and is <= 28 it should write "it is ok" to the console.
		If the input temperature value is > 28 it should write "it is hot here" to the console.*/

		Console.Write("Enter The Temperature:");
		string input = Console.ReadLine();
		int temperatureValue;
		bool temperature = int.TryParse(input,out temperatureValue);
		if (temperature)
		{
			string result = (temperatureValue <=15)
				? ("it is too cold here")
				:temperatureValue >16 &&  temperatureValue <=28? "it is ok" 
				:temperatureValue >28? "it is hot here":"Not a valid Temperature";
			Console.WriteLine(result);
		}
		


		


	}
}

```