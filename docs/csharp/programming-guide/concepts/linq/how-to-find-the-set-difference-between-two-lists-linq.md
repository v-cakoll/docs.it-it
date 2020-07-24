---
title: Come trovare la differenza dei set tra due elenchi (LINQ) (C#)
description: Informazioni su come usare LINQ in C# per confrontare due elenchi di stringhe e restituire le righe presenti in un elenco ma non nell'altra.
ms.date: 07/20/2015
ms.assetid: 8e8945f0-4aba-439d-8d5d-c8d1eeef4e71
ms.openlocfilehash: 24509488d91f9861ee9bf84277238bea7031e5f6
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105083"
---
# <a name="how-to-find-the-set-difference-between-two-lists-linq-c"></a><span data-ttu-id="38e78-103">Come trovare la differenza dei set tra due elenchi (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="38e78-103">How to find the set difference between two lists (LINQ) (C#)</span></span>
<span data-ttu-id="38e78-104">In questo esempio viene illustrato come usare LINQ per confrontare due elenchi di stringhe e restituire le righe presenti in names1.txt ma non in names2.txt.</span><span class="sxs-lookup"><span data-stu-id="38e78-104">This example shows how to use LINQ to compare two lists of strings and output those lines that are in names1.txt but not in names2.txt.</span></span>  
  
### <a name="to-create-the-data-files"></a><span data-ttu-id="38e78-105">Per creare i file di dati</span><span class="sxs-lookup"><span data-stu-id="38e78-105">To create the data files</span></span>  
  
1. <span data-ttu-id="38e78-106">Copiare names1.txt e names2.txt nella cartella della soluzione, come illustrato in [come combinare e confrontare raccolte di stringhe (LINQ) (C#)](./how-to-combine-and-compare-string-collections-linq.md).</span><span class="sxs-lookup"><span data-stu-id="38e78-106">Copy names1.txt and names2.txt to your solution folder as shown in [How to combine and compare string collections (LINQ) (C#)](./how-to-combine-and-compare-string-collections-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="38e78-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="38e78-107">Example</span></span>  
  
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
  
 <span data-ttu-id="38e78-108">Alcuni tipi di operazioni di query in C#, ad esempio <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Union%2A> e <xref:System.Linq.Enumerable.Concat%2A>, possono essere espressi solo nella sintassi basata su metodo.</span><span class="sxs-lookup"><span data-stu-id="38e78-108">Some types of query operations in C#, such as <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Union%2A>, and <xref:System.Linq.Enumerable.Concat%2A>, can only be expressed in method-based syntax.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="38e78-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="38e78-109">Compiling the Code</span></span>  
 <span data-ttu-id="38e78-110">Creare un progetto di applicazione console C# con direttive `using` per gli spazi dei nomi System.Linq e System.IO.</span><span class="sxs-lookup"><span data-stu-id="38e78-110">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38e78-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38e78-111">See also</span></span>

- [<span data-ttu-id="38e78-112">LINQ e stringhe (C#)</span><span class="sxs-lookup"><span data-stu-id="38e78-112">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
