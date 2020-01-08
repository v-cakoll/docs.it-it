---
title: Come trovare la differenza dei set tra due elenchi (LINQ) (C#)
ms.date: 07/20/2015
ms.assetid: 8e8945f0-4aba-439d-8d5d-c8d1eeef4e71
ms.openlocfilehash: 227405428a1b418cbe6ceb3d0e3274595307e5ef
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345933"
---
# <a name="how-to-find-the-set-difference-between-two-lists-linq-c"></a><span data-ttu-id="40bac-102">Come trovare la differenza dei set tra due elenchi (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="40bac-102">How to find the set difference between two lists (LINQ) (C#)</span></span>
<span data-ttu-id="40bac-103">In questo esempio viene illustrato come usare LINQ per confrontare due elenchi di stringhe e restituire le righe presenti in names1.txt ma non in names2.txt.</span><span class="sxs-lookup"><span data-stu-id="40bac-103">This example shows how to use LINQ to compare two lists of strings and output those lines that are in names1.txt but not in names2.txt.</span></span>  
  
### <a name="to-create-the-data-files"></a><span data-ttu-id="40bac-104">Per creare i file di dati</span><span class="sxs-lookup"><span data-stu-id="40bac-104">To create the data files</span></span>  
  
1. <span data-ttu-id="40bac-105">Copiare names1. txt e names2. txt nella cartella della soluzione, come illustrato in [come combinare e confrontare raccolte di stringhe (LINQ)C#()](./how-to-combine-and-compare-string-collections-linq.md).</span><span class="sxs-lookup"><span data-stu-id="40bac-105">Copy names1.txt and names2.txt to your solution folder as shown in [How to combine and compare string collections (LINQ) (C#)](./how-to-combine-and-compare-string-collections-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="40bac-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="40bac-106">Example</span></span>  
  
```csharp  
class CompareLists  
{          
    static void Main()  
    {  
        // Create the IEnumerable data sources.  
        string[] names1 = System.IO.File.ReadAllLines(@"../../../names1.txt");  
        string[] names2 = System.IO.File.ReadAllLines(@"../../../names2.txt");  
  
        // Create the query. Note that method syntax must be used here.  
        IEnumerable<string> differenceQuery =  
          names1.Except(names2);  
  
        // Execute the query.  
        Console.WriteLine("The following lines are in names1.txt but not names2.txt");  
        foreach (string s in differenceQuery)  
            Console.WriteLine(s);  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:  
     The following lines are in names1.txt but not names2.txt  
    Potra, Cristina  
    Noriega, Fabricio  
    Aw, Kam Foo  
    Toyoshima, Tim  
    Guy, Wey Yuan  
    Garcia, Debra  
     */  
```  
  
 <span data-ttu-id="40bac-107">Alcuni tipi di operazioni di query in C#, ad esempio <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Union%2A> e <xref:System.Linq.Enumerable.Concat%2A>, possono essere espressi solo nella sintassi basata su metodo.</span><span class="sxs-lookup"><span data-stu-id="40bac-107">Some types of query operations in C#, such as <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Union%2A>, and <xref:System.Linq.Enumerable.Concat%2A>, can only be expressed in method-based syntax.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="40bac-108">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="40bac-108">Compiling the Code</span></span>  
 <span data-ttu-id="40bac-109">Creare un progetto di applicazione console C# con direttive `using` per gli spazi dei nomi System.Linq e System.IO.</span><span class="sxs-lookup"><span data-stu-id="40bac-109">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40bac-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40bac-110">See also</span></span>

- [<span data-ttu-id="40bac-111">LINQ e stringhe (C#)</span><span class="sxs-lookup"><span data-stu-id="40bac-111">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
