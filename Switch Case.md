#  Switch Case
###### tags: `switch` `case`

```csharp=
// See https://aka.ms/new-console-template for more information


Console.WriteLine("Enter Your Age:");
int age = int.Parse(Console.ReadLine());

switch (age)
{
	    case 1:
		Console.WriteLine("You are a baby");
		break;	
		case 2:
			Console.WriteLine("You are a toddler");
		break;
		case 3:
			Console.WriteLine("You are a child");
		break;
	default:
		break;
}



```