# Console Method
###### tags: `Console` `method`
``` csharp
static void Main(string[] args)
        {
            Console.ForegroundColor= ConsoleColor.Green;
            //字體(前景)顏色變成綠色
            Console.BackgroundColor= ConsoleColor.Red;
            //背景顏色變為紅色
            Console.Clear();
            //清除先前的配置(白前景/黑背景)
            Console.Write("Enter a string and press enter:");
            //Write方法為不換行無空格
            string readInput = Console.ReadLine();
            //使用ReadLine方法輸入string字串
            Console.WriteLine($"You press the {readInput}");
            //WriteLine方法會向下一格
            Console.Write("Enter a string and press enter:");
            int AsciiValue = Console.Read();
            //宣告變數int並使用Console.Read方法產生ASCII(Read只取第一個字母
            適用於暫停)
            Console.WriteLine($"You press the {AsciiValue}");
            //產生整數 
            Console.ReadKey();
            //適用於按任意鍵跳脫視窗





        }
    }
}
```

