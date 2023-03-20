# Enhanced If Statements
###### tags: `if`

```csharp=
// See https://aka.ms/new-console-template for more information
using System;

class Program
{
	static int temperture = 50;
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