---
title: Come ordinare o filtrare i dati di testo in base a parole o campi (LINQ) (C
ms.date: 07/20/2015
ms.assetid: 7c04d42f-4a78-42c8-9ec8-57ef18fe13a9
ms.openlocfilehash: e869d57c413d175c092cdc15a6fe54cab94e04b8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75347355"
---
# <a name="how-to-sort-or-filter-text-data-by-any-word-or-field-linq-c"></a>Come ordinare o filtrare i dati di testo in base a parole o campi (LINQ) (C
L'esempio seguente illustra come ordinare righe di testo strutturato, ad esempio valori delimitati da virgole, in base a un qualsiasi campo. Il campo può essere specificato in modo dinamico in runtime. Si supponga che i campi in scores.csv rappresentino il numero ID di uno studente, seguito da una serie di quattro punteggi di test.  
  
### <a name="to-create-a-file-that-contains-data"></a>Per creare un file che contenga i dati  
  
1. Copiare i dati scores.csv dall'argomento [Come unire il contenuto da file diversi (LINQ) (C '](./how-to-join-content-from-dissimilar-files-linq.md) ) e salvarlo nella cartella della soluzione.  
  
## <a name="example"></a>Esempio  
  
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
  
 Questo esempio illustra anche come restituire una variabile di query da un metodo.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  

Creare un progetto di applicazione console C# con direttive `using` per gli spazi dei nomi System.Linq e System.IO.
  
## <a name="see-also"></a>Vedere anche

- [LINQ e stringhe (C#)](./linq-and-strings.md)
