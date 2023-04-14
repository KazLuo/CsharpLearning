#  get & set
###### tags: `get` `set`

Box.cs:
```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Runtime.CompilerServices;
using System.Text;
using System.Threading.Tasks;

namespace Get_and_Set
{
	//首先創造出一個名為`box`的類型
	//其中box中有長(length),寬(width),高(height),體積(volume)四個屬性
	//因為使用private的關係，Program.cs是無法直接訪問及修改死個屬性的
	//所以我們需要使用get和set來設定這些屬性，使他可以進行調用及修改

	internal class Box
	{
		private int length = 5;
		private int width;
		private int height;
		private int volume;

		public int Length
		{
			get
			{
				return length;
			}

			set 
			{
				length = value;
			}
		}

		public int Width
		{
			get
			{
				return width;
			}
			set
			{
				width = value;
			}
		}

		public int Height
		{
			get
			{
				return height;
			}
			set 
			{
				height = value; 
			}
		}

		public int Volume
		{
			get
			{
				return this.height*this.length*this.width;
			}
			//這邊不需要set,volume本身只是要計算體積,這部分只要使用get就好

		}
		


	}
}

```
Program.cs:
```csharp
using System;
using System.Collections.Generic;

namespace Get_and_Set
{
	internal class Program
	{
		
		
		static void Main(string[] args)
		{
			Box box = new Box();//實例化生成Box類型
			box.Width = 5;//訪問Box中的Width屬性進行修改
			box.Height = 5;//訪問Box中的Height屬性進行修改
			Console.WriteLine($"The Length is {box.Length}");//由於Length這個屬性我在Box這個類型中已經有屬性數值，這邊是測試他訪問功能
			Console.WriteLine($"The Volume is {box.Volume}");//最後使用Console.WriteLine()來輸出Box中的Volume屬性	
		}
	}
}

```

## 補充

**如果都將變數定義為public 就不需要get set了不是嗎?**

是的，如果你將變量定義為 public，則可以直接對其進行讀寫操作，而不需要使用 get 和 set 方法。

然而，這種做法通常不被推薦，因為它打破了物件導向編程的封裝原則。封裝原則要求我們將對對象內部狀態的訪問限制在對象的內部，並通過對外公開的接口來控制對內部狀態的訪問。如果我們直接將變量設置為 public，則任何人都可以直接訪問這些變量，而不需要通過對象的公開接口，這樣就無法保護對象的內部狀態。

舉個例子來說明。假設你正在設計一個表示學生的類型，並且你需要定義一個表示學生名字的屬性。以下是一個使用 public 字段的示例：

```csharp
public class Student
{
    public string name; // 使用 public 字段表示學生名字
}

```
在這種情況下，任何人都可以直接訪問和修改學生的名字，這樣就無法保護學生的內部狀態。例如，如果你在代碼的其他部分中將學生名字設置為空字符串，就會破壞學生對象的內部狀態：

```csharp
var student = new Student();
student.name = ""; // 直接設置學生名字為空字符串，破壞了學生對象的內部狀態

```


相比之下，如果你使用 get 和 set 方法來定義學生名字的屬性，則可以更好地保護學生的內部狀態。以下是一個使用 `get` 和 `set` 方法的示例：

```csharp
public class Student
{
    private string name; // 使用 private 字段表示學生名字

    public string Name // 使用 get 和 set 方法控制對學生名字的訪問
    {
        get { return name; }
        set { name = value; }
    }
}

```
在這種情況下，只有透過對象的公開接口（即 Name 屬性）才能訪問和修改學生的名字，從而更好地保護學生的內部狀態。例如，如果你在代碼的其他部分中將學生名字設置為空字符串，則會觸發 set 方法中的驗證機制，並且不會破壞學生對象的內部狀態：
```csharp
var student = new Student();
student.Name = ""; // 觸發 set 方法中的驗證機制，防止設置空字符串作為學生名字

```
因此，使用 get 和 set 方法可以更好地保護對象的內部狀態，從而提高代碼的可讀性和可維護性。

另外，使用 get 和 set 方法也可以幫助你實現封裝和抽象化。封裝是一種將對象的內部狀態隱藏在對象的公開接口之後的技術，從而保護對象的內部狀態不受外界的干擾。在上面的示例中，我們將學生名字定義為 private 字段，這樣外界就無法直接訪問和修改學生名字，而是通過 Name 屬性來訪問和修改。這樣就實現了對學生內部狀態的封裝。

抽象化是一種將對象的內部實現細節隱藏在對象的公開接口之後的技術，從而為用戶提供更高層次的抽象。在上面的示例中，用戶只需要知道如何訪問和修改學生的名字，而不需要知道學生名字的實現細節。這樣就實現了對學生內部實現細節的抽象化。

總之，使用 get 和 set 方法可以幫助你實現封裝和抽象化，從而提高代碼的可讀性和可維護性。如果你只是編寫一些簡單的應用程序，可能並不需要使用 get 和 set 方法。但是，如果你編寫的應用程序需要更好的可讀性、可維護性和可擴展性，那麼使用 get 和 set 方法會是一個不錯的選擇。

**同一個namespace下我是可以直接訪問這些屬性的?不需要get set?**
如果您在同一個 namespace 下定義了這些屬性，您可以直接訪問這些屬性，並且可以使用它們來進行操作，不需要使用 get 和 set 方法。這是因為在同一個 namespace 下，屬性是可見且可訪問的。然而，如果您的屬性設置為 private，那麼即使在同一個 namespace 下，您也需要使用 get 和 set 方法來訪問和修改它們。如果您的屬性設置為 public，則可以直接訪問和修改它們，而不需要使用 get 和 set 方法。

**剛剛提到的封裝，封裝對於程式設計的意義**

封裝是面向對象程式設計 (OOP) 中的一個重要概念，其目的是隱藏實現細節並保護數據。在封裝中，類中的數據成員和函數成員被限制在類的內部，只有通過類的公共接口才能訪問它們。這樣可以防止外部的不當訪問和修改，從而保護了對象的完整性和安全性。

封裝的意義在於提高程式碼的可維護性和可重用性，以及降低程式出錯的風險。通過封裝，程式設計人員可以將複雜的實現細節隱藏起來，只向外部提供必要的介面，這樣可以使程式設計更加簡潔和易於理解。同時，封裝也有利於代碼的重用，因為可以把一些通用的操作封裝在一個類中，其他類可以通過繼承或組合的方式重用這些操作。

此外，封裝還可以提高程式碼的安全性。對於一些敏感的數據，我們可以把它們封裝在類中，只提供訪問的接口，防止外部不當訪問和修改。這樣可以保證數據的安全性，防止程式出現錯誤或遭受攻擊。

總之，封裝是面向對象程式設計中不可或缺的一部分，它可以提高程式設計的可維護性、可重用性和安全性，同時也有利於程式設計的開發和管理。

**對於封裝的比喻我可以比喻成一個機器有許多插孔可以提供外部使用，但是內部使用螺絲鎖起來防止別人進行直接修改及檢視，是這個意思嗎**

您的比喻非常貼切，封裝的確就像是一個機器有許多插孔，外部可以使用插孔提供的功能，但內部的實現細節被封裝起來，只對外暴露必要的接口。插孔上的螺絲就像是程式中的 private 屬性和方法，只有在內部才能夠直接訪問和修改，而外部只能夠透過 public 的接口來訪問和操作。這樣的設計能夠增強程式的安全性和可維護性，也能夠讓程式設計更加模組化。
