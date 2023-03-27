#  while Loop
###### tags: `while`
```csharp
using System;
using System.Diagnostics.Metrics;

class Program
{
	static void Main(string[] args)
	{
		int counter = 0;//設置人員計數器 =0
		int i = 0;//設置迴圈計數器 = 0
		while (i < 20)//當迴圈計數器 < 20啟動while迴圈
		{
			Console.WriteLine("Please enter to increase amount by one and wnything else");
			Console.ReadLine();
			counter++;
			Console.WriteLine($"here is {counter} in the car");
			i++;
			if(i == 20)
			{
				Console.WriteLine("is full");
			}
			
		}
		Console.Read();

    }
}

```