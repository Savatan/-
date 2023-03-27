using System;

class Program
{
    static void Main()
    {
        Console.CursorVisible = false;

        int x = Console.WindowWidth / 2;
        int y = Console.WindowHeight / 2;

        Console.SetCursorPosition(x, y);
        Console.Write("@");

        while (true)
        {
            // Получаем информацию о нажатых клавишах
            ConsoleKeyInfo keyInfo = Console.ReadKey(true);

            switch (keyInfo.Key)
            {
                case ConsoleKey.LeftArrow:
                    if (x > 0)
                    {
                        Console.SetCursorPosition(x - 1, y);
                        Console.Write("@");
                        Console.SetCursorPosition(x, y);
                        Console.Write(" ");
                        x--;
                    }
                    break;

                case ConsoleKey.RightArrow:
                    if (x < Console.WindowWidth - 1)
                    {
                        Console.SetCursorPosition(x + 1, y);
                        Console.Write("@");
                        Console.SetCursorPosition(x, y);
                        Console.Write(" ");
                        x++;
                    }
                    break;

                case ConsoleKey.UpArrow:
                    if (y > 0)
                    {
                        Console.SetCursorPosition(x, y - 1);
                        Console.Write("@");
                        Console.SetCursorPosition(x, y);
                        Console.Write(" ");
                        y--;
                    }
                    break;

                case ConsoleKey.DownArrow:
                    if (y < Console.WindowHeight - 1)
                    {
                        Console.SetCursorPosition(x, y + 1);
                        Console.Write("@");
                        Console.SetCursorPosition(x, y);
                        Console.Write(" ");
                        y++;
                    }
                    break;

                default:
                    break;
            }
        }
    }
}
