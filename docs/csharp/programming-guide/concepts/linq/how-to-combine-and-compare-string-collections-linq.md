---
title: Come combinare e confrontare raccolte di stringhe (LINQ) (C#)
description: Questo esempio unisce i file che contengono righe di testo. Informazioni su come eseguire una concatenazione semplice, un'Unione e un'intersezione tra i set di righe in LINQ in C#.
ms.date: 07/20/2015
ms.assetid: 25926e5b-fde2-4dc1-86a0-16ead7aa13d2
ms.openlocfilehash: bfbdb9a0a3d531b56578b242c91596d9e41b6cd6
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105360"
---
# <a name="how-to-combine-and-compare-string-collections-linq-c"></a><span data-ttu-id="dd494-104">Come combinare e confrontare raccolte di stringhe (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="dd494-104">How to combine and compare string collections (LINQ) (C#)</span></span>
<span data-ttu-id="dd494-105">In questo esempio viene illustrato come unire i file che contengono righe di testo e quindi ordinare i risultati.</span><span class="sxs-lookup"><span data-stu-id="dd494-105">This example shows how to merge files that contain lines of text and then sort the results.</span></span> <span data-ttu-id="dd494-106">In particolare viene illustrato come eseguire una concatenazione semplice, un'unione e un'intersezione su due set di righe di testo.</span><span class="sxs-lookup"><span data-stu-id="dd494-106">Specifically, it shows how to perform a simple concatenation, a union, and an intersection on the two sets of text lines.</span></span>  
  
### <a name="to-set-up-the-project-and-the-text-files"></a><span data-ttu-id="dd494-107">Per impostare il progetto e i file di testo</span><span class="sxs-lookup"><span data-stu-id="dd494-107">To set up the project and the text files</span></span>  
  
1. <span data-ttu-id="dd494-108">Copiare i nomi seguenti in un file di testo denominato names1.txt e salvarlo nella cartella del progetto:</span><span class="sxs-lookup"><span data-stu-id="dd494-108">Copy these names into a text file that is named names1.txt and save it in your project folder:</span></span>  
  
    ```text  
    Bankov, Peter  
    Holm, Michael  
    Garcia, Hugo  
    Potra, Cristina  
    Noriega, Fabricio  
    Aw, Kam Foo  
    Beebe, Ann  
    Toyoshima, Tim  
    Guy, Wey Yuan  
    Garcia, Debra  
    ```  
  
2. <span data-ttu-id="dd494-109">Copiare i nomi seguenti in un file di testo denominato names2.txt e salvarlo nella cartella del progetto.</span><span class="sxs-lookup"><span data-stu-id="dd494-109">Copy these names into a text file that is named names2.txt and save it in your project folder.</span></span> <span data-ttu-id="dd494-110">Si noti che i due file hanno alcuni nomi in comune.</span><span class="sxs-lookup"><span data-stu-id="dd494-110">Note that the two files have some names in common.</span></span>  
  
    ```text  
    Liu, Jinghao  
    Bankov, Peter  
    Holm, Michael  
    Garcia, Hugo  
    Beebe, Ann  
    Gilchrist, Beth  
    Myrcha, Jacek  
    Giakoumakis, Leo  
    McLin, Nkenge  
    El Yassir, Mehdi  
    ```  
  
## <a name="example"></a><span data-ttu-id="dd494-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="dd494-111">Example</span></span>  
  
```csharp  
class MergeStrings  
    {  
        static void Main(string[] args)  
        {  
            //Put text files in your solution folder  
            string[] fileA = System.IO.File.ReadAllLines(@"../../../names1.txt");  
            string[] fileB = System.IO.File.ReadAllLines(@"../../../names2.txt");  
  
            //Simple concatenation and sort. Duplicates are preserved.  
            IEnumerable<string> concatQuery =  
                fileA.Concat(fileB).OrderBy(s => s);  
  
            // Pass the query variable to another function for execution.  
            OutputQueryResults(concatQuery, "Simple concatenate and sort. Duplicates are preserved:");  
  
            // Concatenate and remove duplicate names based on  
            // default string comparer.  
            IEnumerable<string> uniqueNamesQuery =  
                fileA.Union(fileB).OrderBy(s => s);  
            OutputQueryResults(uniqueNamesQuery, "Union removes duplicate names:");  
  
            // Find the names that occur in both files (based on  
            // default string comparer).  
            IEnumerable<string> commonNamesQuery =  
                fileA.Intersect(fileB);  
            OutputQueryResults(commonNamesQuery, "Merge based on intersect:");  
  
            // Find the matching fields in each list. Merge the two
            // results by using Concat, and then  
            // sort using the default string comparer.  
            string nameMatch = "Garcia";  
  
            IEnumerable<String> tempQuery1 =  
                from name in fileA  
                let n = name.Split(',')  
                where n[0] == nameMatch  
                select name;  
  
            IEnumerable<string> tempQuery2 =  
                from name2 in fileB  
                let n2 = name2.Split(',')  
                where n2[0] == nameMatch  
                select name2;  
  
            IEnumerable<string> nameMatchQuery =  
                tempQuery1.Concat(tempQuery2).OrderBy(s => s);  
            OutputQueryResults(nameMatchQuery, $"Concat based on partial name match \"{nameMatch}\":");
  
            // Keep the console window open in debug mode.  
            Console.WriteLine("Press any key to exit");  
            Console.ReadKey();  
        }  
  
        static void OutputQueryResults(IEnumerable<string> query, string message)  
        {  
            Console.WriteLine(System.Environment.NewLine + message);  
            foreach (string item in query)  
            {  
                Console.WriteLine(item);  
            }  
            Console.WriteLine("{0} total names in list", query.Count());  
        }  
    }  
    /* Output:  
        Simple concatenate and sort. Duplicates are preserved:  
        Aw, Kam Foo  
        Bankov, Peter  
        Bankov, Peter  
        Beebe, Ann  
        Beebe, Ann  
        El Yassir, Mehdi  
        Garcia, Debra  
        Garcia, Hugo  
        Garcia, Hugo  
        Giakoumakis, Leo  
        Gilchrist, Beth  
        Guy, Wey Yuan  
        Holm, Michael  
        Holm, Michael  
        Liu, Jinghao  
        McLin, Nkenge  
        Myrcha, Jacek  
        Noriega, Fabricio  
        Potra, Cristina  
        Toyoshima, Tim  
        20 total names in list  
  
        Union removes duplicate names:  
        Aw, Kam Foo  
        Bankov, Peter  
        Beebe, Ann  
        El Yassir, Mehdi  
        Garcia, Debra  
        Garcia, Hugo  
        Giakoumakis, Leo  
        Gilchrist, Beth  
        Guy, Wey Yuan  
        Holm, Michael  
        Liu, Jinghao  
        McLin, Nkenge  
        Myrcha, Jacek  
        Noriega, Fabricio  
        Potra, Cristina  
        Toyoshima, Tim  
        16 total names in list  
  
        Merge based on intersect:  
        Bankov, Peter  
        Holm, Michael  
        Garcia, Hugo  
        Beebe, Ann  
        4 total names in list  
  
        Concat based on partial name match "Garcia":  
        Garcia, Debra  
        Garcia, Hugo  
        Garcia, Hugo  
        3 total names in list  
*/  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dd494-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="dd494-112">Compiling the Code</span></span>  
 <span data-ttu-id="dd494-113">Creare un progetto di applicazione console C# con direttive `using` per gli spazi dei nomi System.Linq e System.IO.</span><span class="sxs-lookup"><span data-stu-id="dd494-113">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd494-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd494-114">See also</span></span>

- [<span data-ttu-id="dd494-115">LINQ e stringhe (C#)</span><span class="sxs-lookup"><span data-stu-id="dd494-115">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
- [<span data-ttu-id="dd494-116">Directory di file e LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="dd494-116">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)
