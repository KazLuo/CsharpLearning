# int.TryParse

###### tags: `TryParse`

```csharp
internal class Program
{

	private static void Main(string[] args)
	{
		string number = "128";//輸入128字串
		int parsValue;//pars後的值(int)
	

		bool success = int.TryParse(number, out parsValue );//布林為true,success parsing
		if (success)//if success = true
		{
			Console.WriteLine($"Parsing success,the Number is {parsValue}");//輸出parsValue
			
		}
		else
		{
			Console.WriteLine("TryParse Failed");//失敗則輸入
		}





	}
}


```
### int.TryParse & int.Parse 差異
Reference
https://www.dailyrazor.com/blog/int-parse-vs-int-tryparse/

The difference in both methods is in the way they react when the string you are trying to convert to integer can’t be converted to an integer. And in such a circumstance, the int.Parse() method will throw an exception whereas the int.TryParse() will return a boolean value of false.