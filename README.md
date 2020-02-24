# -using System;

namespace лабаааа
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Кiлькiсть елементiв масиву:");
            int N;//к-сть елментів масиву 
            Random rnd = new Random();
            int[] arr = new int[N = Convert.ToInt32(Console.ReadLine())];
            Console.WriteLine("Початковий масив:");
            for (int i = 0; i < arr.Length; i++)
            {
                arr[i] = rnd.Next(-100, 100);//Заполняем случайными числами диапозоном от -100 до 100
            }
            PrintMassiv(arr);                      
            InsertionSort(arr);            
            SortOfRecession(arr);
            MethodByMisha(arr);
        }
        static void PrintMassiv(int[] arr)
        {
            foreach (var i in arr)//виводимо масив 
            {
                Console.Write(" " + i);
            }
        }       
        static int[] InsertionSort(int[] arr)
        {
            //Вложенный цикл используется для фактического процесса сортировки.
            //При каждом проходе внешнего цикла for текущий элемент вставляется в правильную позицию в массиве.
            //Этот процесс продолжается до сортировки массива
            int j, i, val, flag;
            for (i = 1; i < arr.Length; i++)
            {
                val = arr[i];
                flag = 0;
                for (j = i - 1; j >= 0 && flag != 1;)
                {
                    if (val < arr[j])
                    {
                        arr[j + 1] = arr[j];
                        j--;
                        arr[j + 1] = val;
                    }
                    else flag = 1;
                }
            }
            Console.Write("\nУпорядкуваний масив: ");
            for (i = 0; i < arr.Length; i++)
            {
                Console.Write(arr[i] + " ");
            }
            return arr;
        }
        static void SortOfRecession(int[]arr)
        {
            Array.Reverse(arr);
            Console.WriteLine("\nУпорядкуваний масив за спаданням:");
            foreach (int x in arr)
            {
                Console.Write(x + " ");
            }
                 
        }
        static void MethodByMisha(int[] arr)
        {
            
            int sum = 0;
            for(int i = 0; i < arr.Length; i++)
            {
                if (arr[i] % 2 != 0)
                {
                    sum += arr[i];
                }            
            }          
            Console.Write("\nCумa квадратів непарних елементiв масиву:" + sum*2);
           


        }
    }


}
