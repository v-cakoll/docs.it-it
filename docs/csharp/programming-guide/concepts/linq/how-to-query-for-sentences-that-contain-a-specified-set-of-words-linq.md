---
title: Come eseguire una query per trovare frasi che contengono un set specificato di parole (LINQ) (C#)
description: Informazioni su come usare LINQ in C# per trovare frasi in un file di testo che contengono corrispondenze per ogni set di parole, che può essere popolato in fase di esecuzione.
ms.date: 07/20/2015
ms.assetid: 0724b429-4b87-4d26-a7b1-409358f3fc20
ms.openlocfilehash: c334c7948f19fb857709ff04a83e1dae56fc69da
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104530"
---
# <a name="how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq-c"></a><span data-ttu-id="20c9e-103">Come eseguire una query per trovare frasi che contengono un set specificato di parole (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="20c9e-103">How to query for sentences that contain a specified set of words (LINQ) (C#)</span></span>
<span data-ttu-id="20c9e-104">Questo esempio illustra come trovare frasi in un file di testo che contengono corrispondenze per ogni set di parole specificato.</span><span class="sxs-lookup"><span data-stu-id="20c9e-104">This example shows how to find sentences in a text file that contain matches for each of a specified set of words.</span></span> <span data-ttu-id="20c9e-105">Sebbene la matrice dei termini di ricerca sia hardcoded in questo esempio, può essere anche popolata in modo dinamico durante il runtime.</span><span class="sxs-lookup"><span data-stu-id="20c9e-105">Although the array of search terms is hard-coded in this example, it could also be populated dynamically at runtime.</span></span> <span data-ttu-id="20c9e-106">In questo esempio la query restituisce le frasi che contengono le parole "Historically", "data" e "integrated".</span><span class="sxs-lookup"><span data-stu-id="20c9e-106">In this example, the query returns the sentences that contain the words "Historically," "data," and "integrated."</span></span>  
  
## <a name="example"></a><span data-ttu-id="20c9e-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="20c9e-107">Example</span></span>  
  
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
  
 <span data-ttu-id="20c9e-108">La query funziona suddividendo prima il testo in frasi e quindi suddividendo le frasi in una matrice di stringhe contenenti ogni parola.</span><span class="sxs-lookup"><span data-stu-id="20c9e-108">The query works by first splitting the text into sentences, and then splitting the sentences into an array of strings that hold each word.</span></span> <span data-ttu-id="20c9e-109">Per ognuna di queste matrici, il metodo <xref:System.Linq.Enumerable.Distinct%2A> rimuove tutte le parole duplicate e quindi la query esegue un'operazione <xref:System.Linq.Enumerable.Intersect%2A> sulla matrice di parole e sulla matrice `wordsToMatch`.</span><span class="sxs-lookup"><span data-stu-id="20c9e-109">For each of these arrays, the <xref:System.Linq.Enumerable.Distinct%2A> method removes all duplicate words, and then the query performs an <xref:System.Linq.Enumerable.Intersect%2A> operation on the word array and the `wordsToMatch` array.</span></span> <span data-ttu-id="20c9e-110">Se il conteggio dell'intersezione corrisponde al conteggio della matrice `wordsToMatch`, significa che sono state trovate tutte le parole e viene restituita la frase originale.</span><span class="sxs-lookup"><span data-stu-id="20c9e-110">If the count of the intersection is the same as the count of the `wordsToMatch` array, all words were found in the words and the original sentence is returned.</span></span>  
  
 <span data-ttu-id="20c9e-111">Nella chiamata a <xref:System.String.Split%2A> vengono usati i segni di punteggiatura come separatori in modo da rimuoverli dalla stringa.</span><span class="sxs-lookup"><span data-stu-id="20c9e-111">In the call to <xref:System.String.Split%2A>, the punctuation marks are used as separators in order to remove them from the string.</span></span> <span data-ttu-id="20c9e-112">Se questa operazione non è stata eseguita, è possibile ad esempio avere una stringa "Historically" che non corrisponde a "Historically" nella matrice `wordsToMatch`.</span><span class="sxs-lookup"><span data-stu-id="20c9e-112">If you did not do this, for example you could have a string "Historically," that would not match "Historically" in the `wordsToMatch` array.</span></span> <span data-ttu-id="20c9e-113">È possibile che sia necessario usare altri separatori, a seconda dei tipi di punteggiatura individuati nel testo di origine.</span><span class="sxs-lookup"><span data-stu-id="20c9e-113">You may have to use additional separators, depending on the types of punctuation found in the source text.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="20c9e-114">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="20c9e-114">Compiling the Code</span></span>  
<span data-ttu-id="20c9e-115">Creare un progetto di applicazione console C# con direttive `using` per gli spazi dei nomi System.Linq e System.IO.</span><span class="sxs-lookup"><span data-stu-id="20c9e-115">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>

## <a name="see-also"></a><span data-ttu-id="20c9e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20c9e-116">See also</span></span>

- [<span data-ttu-id="20c9e-117">LINQ e stringhe (C#)</span><span class="sxs-lookup"><span data-stu-id="20c9e-117">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
