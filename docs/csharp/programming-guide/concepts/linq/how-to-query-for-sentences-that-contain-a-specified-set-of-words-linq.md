---
title: Come eseguire una query per trovare frasi che contengono un set specificato di parole (LINQ)C#()
ms.date: 07/20/2015
ms.assetid: 0724b429-4b87-4d26-a7b1-409358f3fc20
ms.openlocfilehash: efb0eb60a9695c19e16b507d29ef6994e904cff9
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347687"
---
# <a name="how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq-c"></a>Come eseguire una query per trovare frasi che contengono un set specificato di parole (LINQ)C#()
Questo esempio illustra come trovare frasi in un file di testo che contengono corrispondenze per ogni set di parole specificato. Sebbene la matrice dei termini di ricerca sia hardcoded in questo esempio, può essere anche popolata in modo dinamico durante il runtime. In questo esempio la query restituisce le frasi che contengono le parole "Historically", "data" e "integrated".  
  
## <a name="example"></a>Esempio  
  
```csharp  
class FindSentences  
{  
    static void Main()  
    {  
        string text = @"Historically, the world of data and the world of objects " +  
        @"have not been well integrated. Programmers work in C# or Visual Basic " +  
        @"and also in SQL or XQuery. On the one side are concepts such as classes, " +  
        @"objects, fields, inheritance, and .NET Framework APIs. On the other side " +  
        @"are tables, columns, rows, nodes, and separate languages for dealing with " +  
        @"them. Data types often require translation between the two worlds; there are " +  
        @"different standard functions. Because the object world has no notion of query, a " +  
        @"query can only be represented as a string without compile-time type checking or " +  
        @"IntelliSense support in the IDE. Transferring data from SQL tables or XML trees to " +  
        @"objects in memory is often tedious and error-prone.";  
  
        // Split the text block into an array of sentences.  
        string[] sentences = text.Split(new char[] { '.', '?', '!' });  
  
        // Define the search terms. This list could also be dynamically populated at runtime.  
        string[] wordsToMatch = { "Historically", "data", "integrated" };  
  
        // Find sentences that contain all the terms in the wordsToMatch array.  
        // Note that the number of terms to match is not specified at compile time.  
        var sentenceQuery = from sentence in sentences  
                            let w = sentence.Split(new char[] { '.', '?', '!', ' ', ';', ':', ',' },  
                                                    StringSplitOptions.RemoveEmptyEntries)  
                            where w.Distinct().Intersect(wordsToMatch).Count() == wordsToMatch.Count()  
                            select sentence;  
  
        // Execute the query. Note that you can explicitly type  
        // the iteration variable here even though sentenceQuery  
        // was implicitly typed.   
        foreach (string str in sentenceQuery)  
        {  
            Console.WriteLine(str);  
        }  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:  
Historically, the world of data and the world of objects have not been well integrated  
*/  
```  
  
 La query funziona suddividendo prima il testo in frasi e quindi suddividendo le frasi in una matrice di stringhe contenenti ogni parola. Per ognuna di queste matrici, il metodo <xref:System.Linq.Enumerable.Distinct%2A> rimuove tutte le parole duplicate e quindi la query esegue un'operazione <xref:System.Linq.Enumerable.Intersect%2A> sulla matrice di parole e sulla matrice `wordsToMatch`. Se il conteggio dell'intersezione corrisponde al conteggio della matrice `wordsToMatch`, significa che sono state trovate tutte le parole e viene restituita la frase originale.  
  
 Nella chiamata a <xref:System.String.Split%2A> vengono usati i segni di punteggiatura come separatori in modo da rimuoverli dalla stringa. Se questa operazione non è stata eseguita, è possibile ad esempio avere una stringa "Historically" che non corrisponde a "Historically" nella matrice `wordsToMatch`. È possibile che sia necessario usare altri separatori, a seconda dei tipi di punteggiatura individuati nel testo di origine.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
Creare un progetto di applicazione console C# con direttive `using` per gli spazi dei nomi System.Linq e System.IO.

## <a name="see-also"></a>Vedere anche

- [LINQ e stringhe (C#)](./linq-and-strings.md)
