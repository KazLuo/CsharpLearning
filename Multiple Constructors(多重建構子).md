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


## 補充

若是單一建構子(預設建構子)

Myclass.cs:
```csharp
public class MyClass
{
    private string name, eyecolor, sex, firstname, lastname;
    private int age;

    public MyClass(string name = "", string eyecolor = "", int age = 0, string sex = "", string firstname = "", string lastname = "")
    {
        this.name = name;
        this.eyecolor = eyecolor;
        this.age = age;
        this.sex = sex;
        this.firstname = firstname;
        this.lastname = lastname;
    }

    // member method
    public void introduction()
    {
        if (sex != null)
            Console.WriteLine($"My name is {name}, my eye color is{eyecolor}, and i'm {age} year old,and i'm {sex}");
        else if (age != 0)
            Console.WriteLine($"My name is {name}, my eye color is{eyecolor}, and i'm {age} years old");
        else if (firstname != null & lastname != null)
            Console.WriteLine($"My name is {firstname} {lastname}");
        else if (lastname != null)
            Console.WriteLine($"My lastname is {lastname}");
        else
            Console.WriteLine("-------------------------------------");
    }
}

```

**所以以兩種寫法來說 如果需要多種類型 是不是多重的寫法比較適合?**

如果需要多重建構子的話確實比較適合。使用預設值的方式可以讓你在需要時選擇要傳遞哪些參數，而其他沒有被傳遞的參數可以使用預設值。另外，使用預設值的方式也可以讓程式碼更加簡潔易讀。


**如果單一建構子(預設)可以達成，為何需要多重建構子?**

多重建構子的用途是讓你在創建物件時，可以使用不同數量或不同型別的參數來初始化物件的屬性，從而提高程式碼的彈性和可讀性。

使用多重建構子，可以簡化程式碼，減少因為不同的初始化方式而需要寫多個初始化的方法或設置方法。同時，使用多重建構子，可以更加靈活地使用物件，因為你可以根據需要傳遞不同的參數來創建物件。例如，在一個需要根據用戶輸入來創建不同的物件時，多重建構子就可以派上用場。

總的來說，多重建構子提供了一個更加方便和靈活的方式來初始化物件，從而提高了程式碼的可讀性和可維護性。


