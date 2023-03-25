# C# Coding Standards Best Practices
###### tags: `Common`

Reference From
https://www.dofactory.com/csharp-coding-standards

以下是我們的C#編碼標準，命名慣例和最佳實踐。請在自己的項目中使用這些，或根據自己的需要進行調整。

## 類名(Class Name)

使用PascalCasing為類名和方法名。

```csharp
Copy code
public class ClientActivity
{
    public void ClearStatistics()
    {
        //...
    }
    public void CalculateStatistics()
    {
        //...
    }
}
```
為什麼：與Microsoft的.NET Framework一致，易於閱讀。

## 變量名(Variable Names)

使用camelCasing作為局部變量和方法參數的變量名。

```csharp
Copy code
public class UserLog
{
    public void Add(LogEvent logEvent)
    {
        int itemCount = logEvent.Items.Count;
        // ...
    }
}
```
為什麼：與Microsoft的.NET Framework一致，易於閱讀。

## 識別符(Identifiers)

不使用匈牙利(Hungarian)命名法或任何其他類型識別符

```csharp
Copy code
// 正確
int counter;
string name;

// 避免
int iCounter;
string strName;
```

為什麼：與Microsoft的.NET Framework一致。此外，Visual Studio IDE非常容易通過工具提示來確定變量的類型。最好避免在識別符中使用類型指標。

## 常量(Constants)

不使用大寫字母來表示常量或只讀變量

```csharp
Copy code
// 正確
public static const string ShippingType = "DropShip";

// 避免
public static const string SHIPPINGTYPE = "DropShip";
```
為什麼：與Microsoft的.NET Framework一致。大寫字母會分散太多注意力。

## 縮寫(Abbreviations)

避免使用縮寫。
例外情況：作為名稱常用的縮寫，例如Id，Xml，Ftp，Uri

```csharp
Copy code
// 正確
UserGroup userGroup;
Assignment employeeAssignment;

// 避免
UserGroup usrGrp;
Assignment empAssignment;

// 例外情況
CustomerId customerId;
XmlDocument xmlDocument;
FtpHelper ftpHelper;
UriPart uriPart;
```
為什麼：與Microsoft的.NET Framework一致。它可以防止不同開發人員使用不一致的縮寫。

## 縮寫大小寫(Abbreviation Casing)

對於3個或更多字符的縮寫，使用PascalCasing（2個字符都是大寫字母）

```csharp
Copy code
HtmlHelper htmlHelper;
FtpTransfer ftpTransfer;
UIControl uiControl;
```
為什麼：與Microsoft的.NET Framework一致。大寫字母會分散太多注意力。

## 不要用底線(No Underscores)

禁止在標識符中使用底線。
例外：私有靜態變量可以使用下劃線作為前綴。
```csharp
// 正確的寫法
public DateTime clientAppointment;
public TimeSpan timeLeft;

// 避免使用
public DateTime client_Appointment;
public TimeSpan time_Left;

// 例外
private DateTime _registrationDate;

```
為什麼：：與 Microsoft 的 .NET Framework 一致。它使代碼閱讀起來更自然（沒有“連線”）。也避免了下劃線壓力，即無法看到下劃線。
## 類型名稱(Type Names)

使用預定義的類型名稱而不是系統類型名稱，例如Int16，Single，UInt64等。
```csharp
// 正確的寫法
string firstName;
int lastIndex;
bool isSaved;

// 避免使用
String firstName;
Int32 lastIndex;
Boolean isSaved;
為什麼：這與Microsoft .NET Framework保持一致，使代碼更容易閱讀。
```

## 隱式類型(Implicit Types)

使用隱式類型var來聲明局部變量。
例外：基本類型（int，string，double等）使用預定義的名稱。
```csharp

var stream = File.Create(path);
var customers = new Dictionary();

// 例外
int index = 100;
string timeSheet;
bool isCompleted;
為什麼：減少混亂，特別是對於複雜的泛型類型。在Visual Studio工具提示中可以輕鬆檢測到類型。
```

## 名詞類名稱(Noun Class Names)

使用名詞或名詞短語來為類命名。
```csharp


public class Employee
{
}
public class BusinessLocation
{
}
public class DocumentCollection
{
}
```
為什麼：這與Microsoft .NET Framework保持一致，使類易於記憶。

## 名詞類別名稱(Noun Class Names)

使用名詞或名詞片語來命名類別。
```csharp
public class Employee
{
}
public class BusinessLocation
{
}
public class DocumentCollection
{
}
```
原因：與 Microsoft 的 .NET Framework 一致。讓類別易於記憶。

## 介面(Interfaces)

使用字母 I 作為介面名稱的前綴。介面名稱是名詞（片語）或形容詞。
```csharp
public interface IShape
{
}
public interface IShapeCollection
{
}
public interface IGroupable
{
}
```
原因：與 Microsoft 的 .NET Framework 一致。

## 檔案名稱(File Names)

依據主要類別來命名源檔案。例外情況：部分類別的檔案名稱反映其來源或目的，例如設計者、生成的等等。
```csharp
// 位於 Task.cs
public partial class Task
{
//...
}
// 位於 Task.generated.cs
public partial class Task
{
//...
}
```
原因：與 Microsoft 的慣例一致。檔案按字母順序排序，部分類別保持相鄰。

## 命名空間(Namespaces)

使用明確定義的結構來組織命名空間。
```csharp
// 範例
namespace Company.Product.Module.SubModule
namespace Product.Module.Component
namespace Product.Layer.Module.Group
原因：與 Microsoft 的 .NET Framework 一致。維護程式碼庫的良好組織。
```

## 花括號(Curly Brackets)

垂直對齊花括號。
```csharp
// 正確
class Program
{
static void Main(string[] args)
{
}
}
```
原因：Microsoft 有不同的標準，但開發人員普遍偏好垂直對齊的花括號。

## 成員變數(Member Variables)

將所有成員變數聲明在類別的頂部，靜態變數則放在最頂部。
```csharp
// 正確
public class Account
{
public static string BankName;
public static decimal Reserves;

csharp
Copy code
public string Number {get; set;}
public DateTime DateOpened {get; set;}
public DateTime DateClosed {get; set;}
public decimal Balance {get; set;}

// Constructor
public Account()
{
    // ...
}
}
```
原因：一般接受的做法，可避免尋找變數聲明。

## 列舉(Enums)

使用單數名稱來命名列舉。例外情況：位欄列舉。
```csharp
// 正確
public enum Color
{
Red,
Green,
Blue,
Yellow,
Magenta,
Cyan
}

// 例外
[Flags]
public enum Dockings
{
None = 0,
Top = 1,
Right = 2,
Bottom = 4,
Left
}
```
原因：與 Microsoft  .NET Framework 一致，使代碼更易於閱讀。多個標誌，因為枚舉可以包含多個值（使用按位“或”）。

## 列舉型別(Enum Types)

不要明確指定列舉型別或列舉型別的值（除了位欄列舉）。
```csharp
// 錯誤
public enum Direction : long
{
North = 1,
East = 2,
South = 3,
West = 4
}

// 正確
public enum Direction
{
North,
East,
South,
West
}
```
原因：當依賴實際型別和值時，可能會產生混淆。

## 列舉後綴(Enum Suffix)

不要在列舉名稱中加上 "Enum" 後綴。
```csharp
// 錯誤
public enum CoinEnum
{
Penny,
Nickel,
Dime,
Quarter,
Dollar
}

// 正確
public enum Coin
{
Penny,
Nickel,
Dime,
Quarter,
Dollar
}
```
原因：與Microsoft的.NET Framework一致，並與之前的規則一致，不在識別符中添加類型指示符。