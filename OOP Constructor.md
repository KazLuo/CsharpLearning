# OOP-Constructor(建構子)
###### tags:`Constructor` `OOP`

**Human.cs:**
```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Login_System
{
	//Class基本上如一張藍圖，而作為人類來說會定義出他的屬性(name,age...)，以及他的行為(introduction,walk...)，而這些屬性和行為就是Class的成員
	//Class的成員分為兩種，一種是Field，另一種是Method
	//Field就是屬性，而Method就是行為
	//Field和Method的差別在於，Field是用來儲存資料的，而Method是用來執行動作的
	class Human
	{
		public string firstname;//如果不使用public Program.cs中就無法調用，造成錯誤
		public string lastname;
		public int age;
		public Human(string fsname, string lastname, int age)//設定建構子(Constructors), 用來初始化物件, 並且不需要回傳值
		{	
			//如果不使用this需要再另外新增一個名稱
			firstname = fsname;
			//實際上可使用this, this .firstname = firstname;
			this .lastname = lastname;
			this .age = age;
		}

		public void introduction()//public的部分同樣道理
		{
			Console.WriteLine($"My name is {firstname}. {lastname},and i am {age} years old");
		}
	}
}
```

Program.cs

```csharp
using Login_System;
using System;

class Program
{
	static void Main(string[] args)
	{		
		Human Kaz = new Human("Kaz","Luo",31);//對Human進行實例化生成一個名為Kaz,並運用建構子(Constructors)輸入相關數值
		//Kaz.firstname = "Kaz";//Kaz中定義他的firstname
		Kaz.introduction();//並執行Human.introduction的方法


	}	
}


```


## 補充


![](https://hackmd.io/_uploads/ry4QazOW2.png)

圖片資料來自:https://ithelp.ithome.com.tw/articles/10213236



**1. 建構子的函式名稱需與類別相同
2. 存取修飾詞為public
3. 不能有回傳值 & 不能使用void**

這一點是指，Constructor 是一個特殊的方法，其目的是初始化對象的狀態，而不是返回任何值。因此，在 Constructor 中不能使用 return 關鍵字返回值。

範例:
```csharp

public class MyClass
{
    private int myValue;

    public MyClass(int value)
    {
        myValue = value;
        return; // 不合法的使用方式
    }
}

```

**4. 不會被繼承**

在 C# 中，子類繼承了父類的所有成員（除了父類的私有成員），但是子類不會繼承父類的 Constructor。不過，子類可以調用父類的 Constructor 來初始化父類的成員。在子類的 Constructor 中，你可以使用 base 關鍵字調用父類的 Constructor。使用 base 關鍵字後面跟著括號，你可以傳遞一些參數給父類的 Constructor。例如：

```csharp
class ParentClass
{
    public ParentClass(int x)
    {
        // 父類的 Constructor
    }
}

class ChildClass : ParentClass
{
    public ChildClass(int x, int y) : base(x)
    {
        // 子類的 Constructor
    }
}

```
在上面的代碼中，ChildClass 繼承了 ParentClass，但是 ChildClass 自己沒有定義 Constructor，所以它會繼承 ParentClass 的 Constructor。在 ChildClass 的 Constructor 中，我們使用 base(x) 調用了父類的 Constructor，並傳遞了一個參數 x。這樣，當我們創建 ChildClass 對象時，它會先調用父類的 Constructor 來初始化父類的成員，然後再執行子類的 Constructor。

**5. 如果一個類沒有定義 Constructor，編譯器會自動生成一個默認 Constructor，其沒有任何參數且不執行任何操作。**

```csharp
public class MyClass
{
    private int myValue;

    // MyClass 類沒有定義任何 Constructor
    // 因此編譯器會自動生成一個默認 Constructor。

    public int GetMyValue()
    {
        return myValue;
    }
}

...

MyClass myObj = new MyClass();
int value = myObj.GetMyValue(); // value 的值為 0。

```
在上面的代碼中，MyClass 類沒有定義任何 Constructor，因此編譯器會自動生成一個默認 Constructor。在使用 new 關鍵字創建 MyClass 對象時，默認 Constructor 會自動調用並初始化 myValue 屬性，其值為 0。

**6. 依據需求，類別內可以有多個建構函式(多載overloading)** 

在 C# 中，一個類別可以定義多個 Constructor，每個 Constructor 可以有不同的參數列表。這種為同一個類別定義多個 Constructor 的技術被稱為 Constructor Overloading（建構函式多載）。

當你創建一個類別的對象時，你可以根據需要選擇要使用哪個 Constructor。如果你調用一個 Constructor，但是沒有傳遞需要的參數，編譯器會嘗試尋找另一個 Constructor，該 Constructor 的參數列表能夠匹配你提供的參數。

例如，假設你有一個名為 MyClass 的類別，你可以定義多個 Constructor，如下所示：

```csharp
class MyClass
{
    public MyClass()
    {
        // Constructor 1
    }

    public MyClass(int x)
    {
        // Constructor 2
    }

    public MyClass(int x, string s)
    {
        // Constructor 3
    }
}

```

在上面的代碼中，我們定義了三個 Constructor，它們的參數列表不同。當你創建 MyClass 對象時，你可以根據需要選擇要使用哪個 Constructor。例如，你可以使用以下代碼來創建 MyClass 對象：

```csharp
MyClass obj1 = new MyClass(); // 使用 Constructor 1
MyClass obj2 = new MyClass(10); // 使用 Constructor 2
MyClass obj3 = new MyClass(10, "hello"); // 使用 Constructor 3

```

在上面的代碼中，我們分別創建了三個 MyClass 對象，每個對象使用了不同的 Constructor。這種根據需要選擇 Constructor 的技術，讓我們更靈活地使用類別。



**8. 除非類別是靜態，否則沒有建構函式的類別會從C#編譯器取得一個公開無參數建構函式，以啟用類別具現化**

在 C# 中，如果一個類別沒有定義任何 Constructor，並且它不是靜態類別，那麼編譯器會自動為這個類別生成一個公開的、無參數的 Constructor。這個自動生成的 Constructor 被稱為默認 Constructor。

這個默認 Constructor 的目的是讓類別能夠被實例化。如果一個類別沒有任何 Constructor，那麼這個類別就無法被創建對象。因此，編譯器會自動為這個類別生成一個默認 Constructor，以便讓類別能夠被實例化。

注意，如果一個類別是靜態類別，則不需要 Constructor，因為靜態類別不能被實例化。因此，靜態類別不會自動獲得默認 Constructor。

總結來說，如果一個類別沒有定義任何 Constructor，但它不是靜態類別，那麼編譯器會自動為這個類別生成一個公開的、無參數的 Constructor，以啟用該類別的具現化。




