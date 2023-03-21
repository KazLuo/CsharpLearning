# Login system (Nested If Statements 巢狀結構)
###### tags: `if` `csharp10` `.NET 6` `Nested If`
```csharp=
// See https://aka.ms/new-console-template for more information
string username;
string userpassword;

registed();
login();


   void registed()
{
	Console.WriteLine("Please Enter Your Name");
	username = Console.ReadLine();
	Console.WriteLine("Please Enter Your Password");
	userpassword = Console.ReadLine();

}	
   void login( )
{
	Console.WriteLine("Please Enter Your Name");
	if (username == Console.ReadLine())
	{
		Console.WriteLine("Please Enter Your Password");
		if (userpassword == Console.ReadLine())
		{
			Console.WriteLine($"Welcome Back{username}");
		}
		else
		{
			Console.WriteLine("Please Enter Again");
		}
	}
	else
	{
        Console.WriteLine("Please Enter Again, Application reset");
    }
	


}

```
