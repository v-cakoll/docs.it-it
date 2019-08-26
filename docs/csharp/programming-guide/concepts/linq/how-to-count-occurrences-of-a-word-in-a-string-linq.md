---
title: 'Procedura: Contare le occorrenze di una parola in una stringa (LINQ) (C#)'
ms.date: 07/20/2015
ms.assetid: f8e6f546-7c14-4aa1-8a75-e8d09f3b8ccd
ms.openlocfilehash: 12118c6322df0cfb93cb3d4a4dbbc02d68a0c776
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69593912"
---
# <a name="how-to-count-occurrences-of-a-word-in-a-string-linq-c"></a><span data-ttu-id="55f2d-102">Procedura: Contare le occorrenze di una parola in una stringa (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="55f2d-102">How to: Count Occurrences of a Word in a String (LINQ) (C#)</span></span>
<span data-ttu-id="55f2d-103">Questo esempio illustra come usare una query LINQ per contare le occorrenze di una parola specifica all'interno di una stringa.</span><span class="sxs-lookup"><span data-stu-id="55f2d-103">This example shows how to use a LINQ query to count the occurrences of a specified word in a string.</span></span> <span data-ttu-id="55f2d-104">Si noti che per eseguire il conteggio viene prima chiamato il metodo <xref:System.String.Split%2A> per creare una matrice di parole.</span><span class="sxs-lookup"><span data-stu-id="55f2d-104">Note that to perform the count, first the <xref:System.String.Split%2A> method is called to create an array of words.</span></span> <span data-ttu-id="55f2d-105">Il metodo <xref:System.String.Split%2A> influisce negativamente sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="55f2d-105">There is a performance cost to the <xref:System.String.Split%2A> method.</span></span> <span data-ttu-id="55f2d-106">Se l'unica operazione da eseguire sulla stringa è il conteggio delle parole, è consigliabile usare il metodo <xref:System.Text.RegularExpressions.Regex.Matches%2A> o <xref:System.String.IndexOf%2A>.</span><span class="sxs-lookup"><span data-stu-id="55f2d-106">If the only operation on the string is to count the words, you should consider using the <xref:System.Text.RegularExpressions.Regex.Matches%2A> or <xref:System.String.IndexOf%2A> methods instead.</span></span> <span data-ttu-id="55f2d-107">Se tuttavia le prestazioni non rappresentano un problema critico o se la frase è già stata suddivisa per sottoporla ad altri tipi di query, anche LINQ costituisce una scelta appropriata per contare le parole o le frasi.</span><span class="sxs-lookup"><span data-stu-id="55f2d-107">However, if performance is not a critical issue, or you have already split the sentence in order to perform other types of queries over it, then it makes sense to use LINQ to count the words or phrases as well.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55f2d-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="55f2d-108">Example</span></span>  
  
```csharp  
class CountWords  
{  
    static void Main()  
    {  
        string text = @"Historically, the world of data and the world of objects" +  
          @" have not been well integrated. Programmers work in C# or Visual Basic" +  
          @" and also in SQL or XQuery. On the one side are concepts such as classes," +  
          @" objects, fields, inheritance, and .NET Framework APIs. On the other side" +  
          @" are tables, columns, rows, nodes, and separate languages for dealing with" +  
          @" them. Data types often require translation between the two worlds; there are" +  
          @" different standard functions. Because the object world has no notion of query, a" +  
          @" query can only be represented as a string without compile-time type checking or" +  
          @" IntelliSense support in the IDE. Transferring data from SQL tables or XML trees to" +  
          @" objects in memory is often tedious and error-prone.";  
  
        string searchTerm = "data";  
  
        //Convert the string into an array of words  
        string[] source = text.Split(new char[] { '.', '?', '!', ' ', ';', ':', ',' }, StringSplitOptions.RemoveEmptyEntries);  
  
        // Create the query.  Use ToLowerInvariant to match "data" and "Data"   
        var matchQuery = from word in source  
                         where word.ToLowerInvariant() == searchTerm.ToLowerInvariant()  
                         select word;  
  
        // Count the matches, which executes the query.  
        int wordCount = matchQuery.Count();  
        Console.WriteLine("{0} occurrences(s) of the search term \"{1}\" were found.", wordCount, searchTerm);  
  
        // Keep console window open in debug mode  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:  
   3 occurrences(s) of the search term "data" were found.  
*/  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="55f2d-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="55f2d-109">Compiling the Code</span></span>  
 <span data-ttu-id="55f2d-110">Creare un progetto di applicazione console C# con direttive `using` per gli spazi dei nomi System.Linq e System.IO.</span><span class="sxs-lookup"><span data-stu-id="55f2d-110">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55f2d-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55f2d-111">See also</span></span>

- [<span data-ttu-id="55f2d-112">LINQ e stringhe (C#)</span><span class="sxs-lookup"><span data-stu-id="55f2d-112">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
