# Do While Loop
###### tags: `do` `while`

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace DoWhileLoop
{
    class Program
    {
        static void Main(string[] args)
        {

            int lenghtOfText = 0;
            //do...while loop中會優先執行do的一次程式
            //再依照是否符合while條件判斷，是否再執行do內部程式直到條件達成
            do
            {
                Console.WriteLine("請輸入任意字元:");
                string currentText = Console.ReadLine();
                lenghtOfText += currentText.Length;//當下字元數 + 輸入字元數

            }
            while (lenghtOfText <= 20);//當字元數 =20 則結束迴圈進入下一階段
            Console.WriteLine("Enought while lenghtOfText <= 20");
            Console.Read();
            

        } 
    }
}

```