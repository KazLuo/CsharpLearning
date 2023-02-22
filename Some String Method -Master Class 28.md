# Some String Method -Master Class 28
###### tags: `String` `method`
``` csharp
using System;

namespace ConsoleApp2
{
    class Program
    {
        static void Main(string[] args)
        {
            string imNull = null;
            string imSpace = " ";
            string firstNmae = "Kazue";//0k 1a 2z 3u 4 e
            string lastNmae = "Luo";
            string fullName = string.Concat(" ",firstNmae," ",lastNmae," ");//string.concat()用於串聯多個string使用
            Console.WriteLine(firstNmae.Substring(2));//output: zue 依照字元依序排列0,1,2,3...起始字母為0.若帶2則output 第二字元'z'開始之字元: zue 
            Console.WriteLine(fullName.ToUpper());//將fullName中字串全部轉為大寫
            Console.WriteLine(fullName.ToLower());//將fullNmae中字串全部轉為小寫
            Console.WriteLine(fullName.Trim());//去除fullName字串中頭尾的" "空格 leading and trailing
            Console.WriteLine(fullName.IndexOf('e'));//用來檢索fullName中字串e的位置.fullName中的e在字元5號位置(0為" ")

            //String.IsNullOrWhiteSpace-檢查該變數是否為Null or Space
            Console.WriteLine(String.IsNullOrWhiteSpace(fullName));//String.IsNullOrWhiteSpace用於檢查該變數是否為空值(" "or Null),該行輸出為false
            Console.WriteLine(String.IsNullOrWhiteSpace(imSpace));//因為是" "outPut為 true
            Console.WriteLine(String.IsNullOrWhiteSpace(imNull));//因為是null outPut為 true

            //String.Formate-根據指定格式轉換字串，並插入另一個字串
            string name = "Kaz";
            int money = 20;
            Console.WriteLine(String.Format("My name is{0}", name));
            Console.WriteLine(String.Format("I have {0} Dallor", money));//顯示為數字 "20"
            Console.WriteLine(String.Format("I have {0:C3} Dallor", money));//顯示為貨幣"NT $ 20.000"(C)3為取小數點後幾位





        }
    }
}
```