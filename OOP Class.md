# OOP-Class
###### tags: `OOP` `Class`

這次會分成兩個部分
一個為Human.cs及Program.cs，其中Human.cs創造一個Human類別
並在Program中進行調用，以下為程式碼:

Human.cs

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

		public void introduction()//public的部分同樣道理
		{
			Console.WriteLine("My name is " + firstname);
		}
	}
}
```
Program.cs

```csharp
using Login_System;//注意這邊若沒有調用則無法作用
using System;

class Program
{
	static void Main(string[] args)
	{		
		Human Kaz = new Human();//對Human進行實例化生成一個名為Kaz
		Kaz.firstname = "Kaz";//Kaz中定義他的firstname
		Kaz.introduction();//並執行Human.introduction的方法

	}	
}

```

1. 在 using 指示詞中，我們引用了 Login_System 命名空間，這個命名空間包含了 Human 類別的定義。

2. 在 Program 類別的 Main 方法中，我們創建了一個名為 Kaz 的 Human 對象，並使用 new 關鍵字進行了實例化。

3. 我們為 Kaz 對象的 firstname 屬性賦值為 "Kaz"。

4. 我們調用 Kaz 對象的 introduction 方法，該方法會在控制台上顯示 "My name is Kaz"。

總體而言，這段程式碼是用來示範如何創建 Human 對象以及如何使用該對象的屬性和方法。

