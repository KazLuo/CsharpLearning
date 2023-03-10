# if Statements
###### tags: `if`

```csharp=
internal class Program
{

	private static void Main(string[] args)
	{

		bool admin = true;
		bool isregister = true;
		string userName = "";
		Console.WriteLine("Please Enter Your Name");
		userName = Console.ReadLine();
		if (isregister && admin && userName !="" ) 
		{
            Console.WriteLine($"Welcome {userName}");
			Console.WriteLine($"User is registered");
			Console.WriteLine($"User is Admin");

			if (userName == "Kaz")
				//注意if條件句需要使用比較運算子 使用"=="非"="
				//"==" = 比較兩者是否相同 "=" =賦值
			{
				Console.WriteLine("Welcome Master");
			}

			Console.Read();
		}
	

	}
}

```