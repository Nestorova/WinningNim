using System;
using System.Collections.Generic;



class WinningNim
{
    static void Main()
    {
        List<uint> heaps = Input ();
        TryGetIntoLosingPossition(heaps);

        Console.WriteLine(string.Join(" ",heaps)); 
        
    }

    private static void TryGetIntoLosingPossition(List<uint> heaps)
    {

        uint nimSum = NimSum(heaps);
        if (nimSum != 0)
        {
            uint nimSumCopy = nimSum;
            int LeftMostUpBitIndex = 0;
            while (nimSumCopy > 0)
            {
                nimSumCopy >>= 1;
                LeftMostUpBitIndex++;

            }
            LeftMostUpBitIndex--;

            int nulledNumberInd = 0;
            for (int i = 0; i < heaps.Count; i++)
            {
                if ((heaps[i] & ((uint)1 << LeftMostUpBitIndex)) > 0)
                {
                    heaps[i] = 0;
                    nulledNumberInd = i;

                    break;
                }
            }
            uint nimSumAfterNulling = NimSum(heaps);
            heaps[nulledNumberInd] = nimSumAfterNulling;

        }
        else
        {
            Console.WriteLine("Lose");
        }
    }

    private static uint NimSum(List<uint> heaps)
    {
        uint nimSum = 0;
        for (int i = 0; i < heaps.Count; i++)
        {
            nimSum ^= heaps[i];
        }
        return nimSum;
    }

private static List<uint> Input()
{
        List<uint> heaps = new List<uint>();

        String stateLine = Console.ReadLine();
        String[] heapSizeString = stateLine.Split(' ');
        int heapsCount = heapSizeString.Length;
        for (uint i = 0; i < heapsCount; i++)
        {
            heaps.Add(uint.Parse(heapSizeString[i]));
        }
return heaps;
}
}
