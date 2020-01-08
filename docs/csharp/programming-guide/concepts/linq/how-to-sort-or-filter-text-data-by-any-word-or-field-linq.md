---
title: Come ordinare o filtrare i dati di testo in base a qualsiasi parola o campo (C#LINQ) ()
ms.date: 07/20/2015
ms.assetid: 7c04d42f-4a78-42c8-9ec8-57ef18fe13a9
ms.openlocfilehash: e869d57c413d175c092cdc15a6fe54cab94e04b8
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347355"
---
# <a name="how-to-sort-or-filter-text-data-by-any-word-or-field-linq-c"></a><span data-ttu-id="d7737-102">Come ordinare o filtrare i dati di testo in base a qualsiasi parola o campo (C#LINQ) ()</span><span class="sxs-lookup"><span data-stu-id="d7737-102">How to sort or filter text data by any word or field (LINQ) (C#)</span></span>
<span data-ttu-id="d7737-103">L'esempio seguente illustra come ordinare righe di testo strutturato, ad esempio valori delimitati da virgole, in base a un qualsiasi campo.</span><span class="sxs-lookup"><span data-stu-id="d7737-103">The following example shows how to sort lines of structured text, such as comma-separated values, by any field in the line.</span></span> <span data-ttu-id="d7737-104">Il campo può essere specificato in modo dinamico in runtime.</span><span class="sxs-lookup"><span data-stu-id="d7737-104">The field may be dynamically specified at runtime.</span></span> <span data-ttu-id="d7737-105">Si supponga che i campi in scores.csv rappresentino il numero ID di uno studente, seguito da una serie di quattro punteggi di test.</span><span class="sxs-lookup"><span data-stu-id="d7737-105">Assume that the fields in scores.csv represent a student's ID number, followed by a series of four test scores.</span></span>  
  
### <a name="to-create-a-file-that-contains-data"></a><span data-ttu-id="d7737-106">Per creare un file che contenga i dati</span><span class="sxs-lookup"><span data-stu-id="d7737-106">To create a file that contains data</span></span>  
  
1. <span data-ttu-id="d7737-107">Copiare i dati scores. csv dall'argomento [come unire il contenuto da file non analoghi (LINQ)C#()](./how-to-join-content-from-dissimilar-files-linq.md) e salvarlo nella cartella della soluzione.</span><span class="sxs-lookup"><span data-stu-id="d7737-107">Copy the scores.csv data from the topic [How to join content from dissimilar files (LINQ) (C#)](./how-to-join-content-from-dissimilar-files-linq.md) and save it to your solution folder.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7737-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="d7737-108">Example</span></span>  
  
```csharp  
public class SortLines  
{  
    static void Main()  
    {  
        // Create an IEnumerable data source  
        string[] scores = System.IO.File.ReadAllLines(@"../../../scores.csv");  
  
        // Change this to any value from 0 to 4.  
        int sortField = 1;  
  
        Console.WriteLine("Sorted highest to lowest by field [{0}]:", sortField);  
  
        // Demonstrates how to return query from a method.  
        // The query is executed here.  
        foreach (string str in RunQuery(scores, sortField))  
        {  
            Console.WriteLine(str);  
        }  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
  
    // Returns the query variable, not query results!  
    static IEnumerable<string> RunQuery(IEnumerable<string> source, int num)  
    {  
        // Split the string and sort on field[num]  
        var scoreQuery = from line in source  
                         let fields = line.Split(',')  
                         orderby fields[num] descending  
                         select line;  
  
        return scoreQuery;  
    }  
}  
/* Output (if sortField == 1):  
   Sorted highest to lowest by field [1]:  
    116, 99, 86, 90, 94  
    120, 99, 82, 81, 79  
    111, 97, 92, 81, 60  
    114, 97, 89, 85, 82  
    121, 96, 85, 91, 60  
    122, 94, 92, 91, 91  
    117, 93, 92, 80, 87  
    118, 92, 90, 83, 78  
    113, 88, 94, 65, 91  
    112, 75, 84, 91, 39  
    119, 68, 79, 88, 92  
    115, 35, 72, 91, 70  
 */  
```  
  
 <span data-ttu-id="d7737-109">Questo esempio illustra anche come restituire una variabile di query da un metodo.</span><span class="sxs-lookup"><span data-stu-id="d7737-109">This example also demonstrates how to return a query variable from a method.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d7737-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="d7737-110">Compiling the Code</span></span>  

<span data-ttu-id="d7737-111">Creare un progetto di applicazione console C# con direttive `using` per gli spazi dei nomi System.Linq e System.IO.</span><span class="sxs-lookup"><span data-stu-id="d7737-111">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d7737-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7737-112">See also</span></span>

- [<span data-ttu-id="d7737-113">LINQ e stringhe (C#)</span><span class="sxs-lookup"><span data-stu-id="d7737-113">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
