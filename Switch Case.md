#  Switch Case
###### tags: `switch` `case` `csharp10` `.NET 6`

```csharp=
// See https://aka.ms/new-console-template for more information


Console.WriteLine("Enter Your Age:");
int age = int.Parse(Console.ReadLine());

switch (age)
{
	    case 1:
		Console.WriteLine("You are a baby");
        //當age = 1 顯示字樣"You are a baby"
		break;
        //當case 1條件符合，執行case 1內容後中斷判定
		case 2:
			Console.WriteLine("You are a toddler");
		break;
		case 3:
			Console.WriteLine("You are a child");
		break;
	default:
        //當都不屬於case條件時則觸發default
		break;
}



```