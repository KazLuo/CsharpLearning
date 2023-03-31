# Loop Practice
###### tags: `while` `for` `continue` `break`

題目:

Imagine you are a developer and get a job in which you need to create a program for a teacher. He needs a program written in c# that calculates the average score of his students. So he wants to be able to enter each score individually and then get the final average score once he enters -1.
So the tool should check if the entry is a number and should add that to the sum. Finally once he is done entering scores, the program should write onto the console what the average score is.
The numbers entered should only be between 0 and 20. Make sure the program doesn't crash if the teacher enters an incorrect value.
Test your program thoroughly.
## 我的寫法
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
            int inputScore;
            int inputTime =0 ;
            double currentScore = 0;
            
            do
            {
                Console.WriteLine("Please Enter your Score");

                if (int.TryParse(Console.ReadLine(), out inputScore))
                {
                    currentScore += inputScore;
               
                    inputTime++;
                }
                else
                {
                    Console.WriteLine("Please enter Number");
                }
                if(inputScore == -1)
                {
                    inputTime -- ;
                    currentScore += 1;
                    Console.WriteLine("The Average is: " + currentScore / inputTime);
                }
               
            } while (inputScore <= 20 && inputScore >= 0);
            
            Console.Read();
            

		}
        
       
		
	}
}

```
這邊寫法不應該使用do while迴圈進行雖然功能性達到，但是無法很好的表達整體事件的脈絡，另外我的程式在輸入<20 && >0的數值會直接結束
程式無法好好的運行

## 我認為標準完整的寫法

```csharp
using System;

class Program
{
	static void Main(string[] args)
	{
		int scoreCount = 0;
		double scoreSum = 0;
		int score;

		Console.WriteLine("請輸入每個學生的分數，輸入 -1 結束並計算平均分數。");

		while (true)
		{
			Console.Write("第 {0} 位學生的分數：", scoreCount + 1);
			string input = Console.ReadLine();

			if (input == "-1")
			{
				break;
			}

			if (!int.TryParse(input, out score) || score < 0 || score > 20)
			{
				Console.WriteLine("無效的分數，請輸入介於 0 到 20 之間的分數。");
				continue;
			}

			scoreSum += score;
			scoreCount++;
		}

		if (scoreCount == 0)
		{
			Console.WriteLine("未輸入任何分數。");
		}
		else
		{
			double averageScore = scoreSum / scoreCount;
			Console.WriteLine("平均分數為：{0:0.##}", averageScore);
		}

		Console.ReadKey();
	}
}

```
撰寫程式碼其中我發現了一些有關Break & Continue的細節
[Continue & Break](/MZMtQbV3SHy6AB17DqFa_A)
