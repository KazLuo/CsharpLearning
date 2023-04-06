# internal class(內部類型)

###### tags: `internal` `class`


**internal class和一般class可以用簡單的方式解釋嗎?**

當你定義一個 class 時，可以使用兩種不同的訪問修飾詞：public 和 internal。

如果你定義了一個 public class，則該類別可以被任何地方的程式碼訪問。

但如果你定義了一個 internal class，則該類別只能被定義在同一個程式集中的程式碼訪問。

簡而言之，internal class 用於限制只有同一個程式集中的程式碼才能訪問它，而 public class 則可以被任何地方的程式碼訪問。這樣可以提高程式碼的安全性和可維護性，同時也可以使程式集更加組織化和模塊化。

**public class 也可以被其他程式集訪問嗎?**
是的，public class 可以被其他程式集訪問。如果你有一個 public class，它就可以被同一個應用程序內的其他程式集訪問。

在 .NET 中，一個應用程序通常由多個程式集組成。如果你有一個 public class，它定義在某個程式集中，那麼其他程式集就可以使用該 public class。這個行為可以通過使用關鍵字 using 和引用相關的程式集來實現。

總之，public class 可以被其他程式集訪問，但 internal class 只能在定義它的程式集內部訪問。


當你想要在一個程式集中使用另一個程式集中的類別時，你需要在你的代碼中引用那個程式集。以下是一個簡單的示例：

假設你有一個 ClassLibrary1 程式集，其中包含一個 public class：

```csharp
namespace ClassLibrary1
{
    public class MyClass
    {
        public void MyMethod()
        {
            Console.WriteLine("Hello from MyClass!");
        }
    }
}
```
現在，你可以在另一個程式集中的代碼中使用 MyClass，只要你將 ClassLibrary1 程式集添加為引用即可。以下是一個簡單的示例 ConsoleApp1 程式集中的代碼：

```csharp
using System;
using ClassLibrary1;

namespace ConsoleApp1
{
    class Program
    {
        static void Main(string[] args)
        {
            MyClass myObject = new MyClass();
            myObject.MyMethod();
        }
    }
}
```
在這個示例中，ConsoleApp1 程式集引用了 ClassLibrary1 程式集。這樣，MyClass 就可以在 ConsoleApp1 程式集中使用了。
