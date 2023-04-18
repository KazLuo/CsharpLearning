# OOP-Member
###### tags: `OOP` `Member`

Program.cs:
```csharp
namespace MemberPractice
{
	internal class Program
	{
		static void Main(string[] args)
		{
			Member tina = new Member();//實例化，生成Tina
			tina.Salary = 10;//藉由get/set使program可以訪問並修飾數值
			tina.introduction(true);//introduction(isfriend = true),所以可以公開薪資
			Member kaz = new Member("Kaz","IT", "Developer", 32, 10000000);//實例化，並依照參數建構子設立相關數值
			kaz.introduction(false);//introduction(isfriend != true),所以不公開薪資並介紹基本資料
		}
	}
}
```

Member.cs:
```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace MemberPractice
{
	internal class Member
	{
		//創建私有屬性
		private int salary ;
		private string name;
		private string jobTitle;
		private string department;
        //創建公用屬性
        public int age;

		//創建get/set使Program可進行訪問及修飾
		public int Salary
		{
			get { return salary; }
			set { salary = value; }
		}

	

		//創建預設建構子
		public Member()
		{
			Console.WriteLine("Object created");
			name = "Tina";
			department = "Process";
			jobTitle = "Engineer";
			age = 34;
			salary = 10000000;
			
		}
		//創建自定義參數建構子
		public Member(string name, string department, string jobTitle, int age, int salary)
		{
			Console.WriteLine("Object created");
			this.name = name;
			this.department = department;
			this.jobTitle = jobTitle;
			this.age = age;
			this.salary = salary;
			
		}
		//創建方法來做自我介紹，如果是朋友(isfriend = true)就公開薪資
		public void introduction(bool isfriend)
		{
			if(isfriend)
			{
				privateintroduction();
			}
			else
			{
                Console.WriteLine($"My name is {name}, i'm in {department},and i'm {jobTitle},my age is {age}");
            }
		}

		//創建方法公布薪資
		private void privateintroduction()
		{
			Console.WriteLine($"My salary is {salary}");
		}

		//解構函數(失敗，尚需測試)
		/*
		~Member()
		{
			Console.WriteLine("Deconstruction of Members object");
			Debug.Write("Destruction of Members object");
		}
		*/
		
	}
}

```

## 補充
### 成員

**請問C#中成員是什麼?**

在 C# 中，成員（Member）是指定義在類別或結構中的變數、方法、屬性、事件等。類別或結構可以包含多個成員，這些成員可以是公用（Public）、私用（Private）、保護（Protected）或內部（Internal）等不同的存取修飾詞，以控制對這些成員的存取權限。

在你提供的程式碼中，成員包括：

-   私有成員（private member）：包括 name、jobTitle 和 salary 三個私有變數，它們只能在類別中被訪問和修改。
-   公共成員（public member）：包括 age 這個公共變數，可以在類別內外被訪問和修改。
-   屬性（property）：包括 Salary 這個屬性，可以公開地訪問 salary 變數，但是可以通過 get 和 set 方法限制對 salary 變數的訪問權限。
-   方法（method）：包括 Introduction 和 privateintroduction 兩個方法，前者是公共方法，可以被其他類別訪問，而後者是私有方法，只能在本類別中被訪問。

這些成員可以協同工作，實現類別的功能。例如，Introduction 方法可以根據傳入的 isFriend 參數，決定是否調用 SharingPrivateInfo 方法，以達到保護私有資料的目的。

**所以屬性也算是成員的一環?**

是的，屬性（property）也是 C# 中的成員（member）之一，它可以用於公開地訪問封裝在類別或結構中的私有成員（private member），例如你提供的程式碼中的 Salary 變數。通常情況下，屬性的名稱以大寫字母開頭，以便與普通變數作區分。屬性可以包括 get 和 set 方法，用於控制對屬性的讀取和修改操作。使用屬性可以提供更好的封裝性和安全性，以及更易讀的代碼。

**這個與物件導向有什麼關係?**
當我們設計一個物件導向的系統時，可以使用類別圖（Class Diagram）來描述系統中的類別（Class）和它們之間的關係。下面是一個簡單的類別圖示例，展示了一個用於管理會員（Members）的類別：
```csharp
+------------------------------------------------+
|                   Members                      |
+------------------------------------------------+
| - name : string                          |
| - jobTitle   : string                          |
| - salary     : int                             |
| + age        : int                             |
+------------------------------------------------+
| + Salary   : int { get; set; }            |
| + Introduction(isFriend: bool) : void           |
+------------------------------------------------+
```
在這個類別圖中，有一個名為 Members 的類別，它有三個私有成員（memberName、jobTitle 和 salary）和一個公共成員（age）。Members 類別還有一個名為 Salary 的屬性，以及一個名為 Introduction 的公共方法。Salary 屬性包含 get 和 set 方法，用於公開地訪問和修改 salary 變數。Introduction 方法用於介紹會員的基本信息，如果傳入的 isFriend 參數為 true，則會顯示會員的薪水信息。

注意，這只是一個簡單的示例，真實的物件導向系統往往包含更多的類別和關係，因此需要更複雜的類別圖來描述。



### get-set補充

**get set 自動實作**

內容中有一段屬性宣告(Salary)如下:
```csahrp
	public int Salary
    {
			get { return salary; }
			set { salary = value; }
    }
```
其實有更加簡便的寫法，也就是IDE中內建的
將 `get` 和 `set` 直接寫在變數宣告的方式稱為自動實作屬性 (Auto-implemented Properties)。這個語法是在 C# 3.0 中引進的，是一個簡化程式碼的方式，可以讓你在不需要定義私有欄位的情況下宣告一個屬性。

舉例來說，以下的程式碼是等價的：
```csharp
// 自動實作屬性
public string Name { get; set; }

// 傳統的宣告方式，需定義私有欄位和get set
private string _name;
public string Name 
{
    get { return _name; }
    set { _name = value; }
}

```
兩種寫法最大的差別在於在自動實作屬性中不需要額外定義私有欄位，而在傳統的宣告方式中需要定義私有欄位並且要寫出 `get` 和 `set` 存取器的程式碼。另外，在自動實作屬性中，編譯器會自動幫你生成私有欄位，因此你在程式碼中無法直接存取這個私有欄位。

在使用上，兩種寫法在功能上是等價的，但是自動實作屬性的寫法通常比較簡潔明瞭，特別是當你只需要簡單地宣告一個屬性時，可以省去額外定義私有欄位和寫存取器的程式碼。

**所以說 如果我不需要特別的動作，例如變數的運算，我只需要回傳值的情況，我只需要單傳使用自動實作屬性即可，對嗎?**

是的，如果你只是需要一個簡單的屬性來存儲或返回某個值，而不需要在讀取或設置該屬性時進行額外的處理或運算，那麼使用自動實現屬性就足夠了。這樣可以讓你的程式碼更加簡潔和易讀。

### 解構函數(研究中)
在Member.cs中我在最下方有寫了一段解構函數，用來將生成後不使用的物件銷毀，研究中，不知道為何無法觸發

解構函數 (Destructor) 是一個特殊的函數，用於釋放對象佔用的資源。當一個對象不再需要使用時，該對象的解構函數會被自動調用，以清理該對象所佔用的系統資源。

在 C# 中，解構函數使用 "~" 字符定義，與構造函數類似，但不帶有任何參數。

在上面提到的程式碼中，解構函數被用來釋放對象所佔用的資源，例如在解構函數中，可能會將一些資源（例如檔案、連接、記憶體等）釋放，以避免這些資源佔用系統資源而導致系統效能降低。

值得注意的是，在 C# 中，垃圾收集器 (Garbage Collector) 負責管理對象的生命週期和資源回收，因此，在一些情況下，解構函數可能不需要被使用，因為垃圾收集器會自動回收不再使用的對象，釋放佔用的資源。但是，在一些情況下，例如使用非受控資源（如檔案、網路連線等）時，解構函數還是很有用的。

