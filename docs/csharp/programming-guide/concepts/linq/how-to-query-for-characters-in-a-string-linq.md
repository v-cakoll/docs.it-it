---
title: Come eseguire una query per i caratteri in una stringa (LINQ) (C#)
description: È possibile eseguire una query su una stringa come una sequenza di caratteri in LINQ. In questo esempio C# viene eseguita una query su una stringa per determinare il numero di cifre numeriche che contiene.
ms.date: 07/20/2015
ms.assetid: 727a1be7-dbec-4ab8-b414-bc2d56feb6ff
ms.openlocfilehash: 3512be7c30843fcd8e881eab59761706a84a3ac8
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104552"
---
# <a name="how-to-query-for-characters-in-a-string-linq-c"></a><span data-ttu-id="5df9b-104">Come eseguire una query per i caratteri in una stringa (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="5df9b-104">How to query for characters in a string (LINQ) (C#)</span></span>
<span data-ttu-id="5df9b-105">Poiché la classe <xref:System.String> implementa l'interfaccia generica <xref:System.Collections.Generic.IEnumerable%601>, è possibile eseguire una query su qualsiasi stringa come una sequenza di caratteri.</span><span class="sxs-lookup"><span data-stu-id="5df9b-105">Because the <xref:System.String> class implements the generic <xref:System.Collections.Generic.IEnumerable%601> interface, any string can be queried as a sequence of characters.</span></span> <span data-ttu-id="5df9b-106">Tuttavia, questo uso di LINQ non è comune.</span><span class="sxs-lookup"><span data-stu-id="5df9b-106">However, this is not a common use of LINQ.</span></span> <span data-ttu-id="5df9b-107">Per le operazioni con criteri di ricerca complessi, usare la classe <xref:System.Text.RegularExpressions.Regex>.</span><span class="sxs-lookup"><span data-stu-id="5df9b-107">For complex pattern matching operations, use the <xref:System.Text.RegularExpressions.Regex> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5df9b-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="5df9b-108">Example</span></span>  
 <span data-ttu-id="5df9b-109">Nell'esempio seguente viene eseguita una query su una stringa per determinare il numero di cifre che contiene.</span><span class="sxs-lookup"><span data-stu-id="5df9b-109">The following example queries a string to determine the number of numeric digits it contains.</span></span> <span data-ttu-id="5df9b-110">Si noti che, dopo la prima esecuzione, la query viene "riutilizzata".</span><span class="sxs-lookup"><span data-stu-id="5df9b-110">Note that the query is "reused" after it is executed the first time.</span></span> <span data-ttu-id="5df9b-111">Ciò è possibile perché la query stessa non archivia i risultati effettivi.</span><span class="sxs-lookup"><span data-stu-id="5df9b-111">This is possible because the query itself does not store any actual results.</span></span>  
  
```csharp  
class QueryAString  
{  
    static void Main()  
    {  
        string aString = "ABCDE99F-J74-12-89A";  
  
        // Select only those characters that are numbers  
        IEnumerable<char> stringQuery =  
          from ch in aString  
          where Char.IsDigit(ch)  
          select ch;  
  
        // Execute the query  
        foreach (char c in stringQuery)  
            Console.Write(c + " ");  
  
        // Call the Count method on the existing query.  
        int count = stringQuery.Count();  
        Console.WriteLine("Count = {0}", count);  
  
        // Select all characters before the first '-'  
        IEnumerable<char> stringQuery2 = aString.TakeWhile(c => c != '-');  
  
        // Execute the second query  
        foreach (char c in stringQuery2)  
            Console.Write(c);  
  
        Console.WriteLine(System.Environment.NewLine + "Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:  
  Output: 9 9 7 4 1 2 8 9  
  Count = 8  
  ABCDE99F  
*/  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5df9b-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="5df9b-112">Compiling the Code</span></span>  
 <span data-ttu-id="5df9b-113">Creare un progetto di applicazione console C# con direttive `using` per gli spazi dei nomi System.Linq e System.IO.</span><span class="sxs-lookup"><span data-stu-id="5df9b-113">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5df9b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5df9b-114">See also</span></span>

- [<span data-ttu-id="5df9b-115">LINQ e stringhe (C#)</span><span class="sxs-lookup"><span data-stu-id="5df9b-115">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
- [<span data-ttu-id="5df9b-116">Come combinare query LINQ con espressioni regolari (C#)</span><span class="sxs-lookup"><span data-stu-id="5df9b-116">How to combine LINQ queries with regular expressions (C#)</span></span>](./how-to-combine-linq-queries-with-regular-expressions.md)
