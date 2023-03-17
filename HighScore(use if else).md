# Highscore (use if else
###### tags: `if`
```csharp=
// See https://aka.ms/new-console-template for more information
using System;

class Program
{
	static int highscore = 300;
	static string highscorePlayer = "Kaz";

	static void Main(string[] args)
	{
		checkHighscore();
	}

	static void checkHighscore()
	{
		Console.WriteLine("Please enter your name");
		string playerName = Console.ReadLine();
		Console.WriteLine("Please enter your score");
		int score = int.Parse(Console.ReadLine());

		if (score < highscore)
		{
			Console.WriteLine("The high score is " + highscore + " and was set by " + highscorePlayer);
		}
		else if (score > highscore)
		{
			highscore = score;
			highscorePlayer = playerName;
			Console.WriteLine("The high score is " + highscore + " and was set by " + highscorePlayer);
		}
	}
}

```