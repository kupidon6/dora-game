# dora-game 
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text.RegularExpressions;

namespace HelloWorld
{
	public class Program
	{
  static void Main()
    {
        string nick1, nick2;
        bool f = true;
        Random rand = new Random();
        int n = rand.Next(1, 66), m;
        while (n > 0)
        {
            Console.WriteLine(n);
            Console.WriteLine("{0}, ваш ход", f ? nick1 : nick2);
            if (f)
            {
                m = int.Parse(Console.ReadLine());
                while (!(m >= 1 && m <= 4))
                {
                    Console.WriteLine("Некорректный ход! {0}, повторите ввод", f ? nick1 : nick2);
                    m = int.Parse(Console.ReadLine());
                }
            }
            else
            {
                m = rand.Next(1, 5); 
                Console.WriteLine(nick2 + " походил " + m);
            }
 
            n -= m;
            f = !f;
        }
        Console.WriteLine(0);
        Console.WriteLine("{0} победил!", f ? nick2 : nick1);
        Console.ReadKey();
    }
