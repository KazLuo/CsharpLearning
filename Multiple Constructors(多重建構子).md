# Multiple Constructors(多重建構子)
###### tags: `OOP` `Constructor` `Multiple`



建立多重建構子(Constructors)
MyClass.cs:
```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

public class MyClass
{
	// member variable
	private string name, eyecolor, sex, firstname, lastname;
	private int age;

	//這邊使用MyClass產生多重建構子(Multiple Constructors)
	//其中內部初始化參數可以不一致產生出多種組合

	// default constructor
	public MyClass() 
	{
        Console.WriteLine("-------------default-----------------");
	}

	// constructor with 3 parameters
	public MyClass(string name, string eyecolor, int age) 
	{
		this.name = name;
		this.eyecolor = eyecolor;
		this.age = age;	
	}

	// constructor with 4 parameters
	public MyClass(string name, string eyecolor, int age,string sex)
	{
		this.name = name;
		this.eyecolor = eyecolor;
		this.age = age;
		this.sex = sex;
	}

	// constructor with 2 parameters
	public MyClass(string firstname, string lastname)
	{
		this.firstname = firstname;
		this.lastname = lastname;
	}

	// constructor with 1 parameters
	public MyClass(string lastname)
	{
		this.lastname = lastname;
	}

	// member method
	public void introduction()
	{
		if (sex != null)
			Console.WriteLine($"My name is {name}, my eye color is{eyecolor}, and i'm {age} year old,and i'm {sex}");
		else if (age != 0)
			Console.WriteLine($"My name is {name}, my eye color is{eyecolor}, and i'm {age} years old");
		else if(firstname != null & lastname !=null)
			Console.WriteLine($"My name is {firstname} {lastname}");
		else if (lastname != null) 
			Console.WriteLine($"My lastname is {lastname}");
		else
			Console.WriteLine("-------------------------------------");

	}
}

```
產生並執行:
console.cs:
```csharp
using System;
using System.Collections.Generic;
using System.Globalization;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Login_System
{
	class console
	{

		static void Main(string[] args)
		{
			MyClass multiConstructors = new MyClass();
			multiConstructors.introduction();
			MyClass John = new MyClass("John", "Blue", 20);
            John.introduction();
			MyClass Ema = new MyClass("Ema","Red",21,"girl");
			Ema.introduction();
			MyClass Tom = new MyClass("Tom","Hank");
			Tom.introduction();
			MyClass Mary = new MyClass("Mary");
			Mary.introduction();
		}
	}

}

```
