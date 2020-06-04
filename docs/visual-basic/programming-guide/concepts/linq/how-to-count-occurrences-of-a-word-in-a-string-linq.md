---
title: 'Procedura: Contare le occorrenze di una parola in una stringa (LINQ)'
ms.date: 07/20/2015
ms.assetid: bc367e46-f7cc-45f9-936f-754e661b7bb9
ms.openlocfilehash: c6894359e5785419ccf8f283f976c0a897288a5d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405326"
---
# <a name="how-to-count-occurrences-of-a-word-in-a-string-linq-visual-basic"></a><span data-ttu-id="da6ad-102">Procedura: contare le occorrenze di una parola in una stringa (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da6ad-102">How to: Count Occurrences of a Word in a String (LINQ) (Visual Basic)</span></span>

<span data-ttu-id="da6ad-103">Questo esempio illustra come usare una query LINQ per contare le occorrenze di una parola specifica all'interno di una stringa.</span><span class="sxs-lookup"><span data-stu-id="da6ad-103">This example shows how to use a LINQ query to count the occurrences of a specified word in a string.</span></span> <span data-ttu-id="da6ad-104">Si noti che per eseguire il conteggio viene prima chiamato il metodo <xref:System.String.Split%2A> per creare una matrice di parole.</span><span class="sxs-lookup"><span data-stu-id="da6ad-104">Note that to perform the count, first the <xref:System.String.Split%2A> method is called to create an array of words.</span></span> <span data-ttu-id="da6ad-105">Il metodo <xref:System.String.Split%2A> influisce negativamente sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="da6ad-105">There is a performance cost to the <xref:System.String.Split%2A> method.</span></span> <span data-ttu-id="da6ad-106">Se l'unica operazione da eseguire sulla stringa è il conteggio delle parole, è consigliabile usare il metodo <xref:System.Text.RegularExpressions.Regex.Matches%2A> o <xref:System.String.IndexOf%2A>.</span><span class="sxs-lookup"><span data-stu-id="da6ad-106">If the only operation on the string is to count the words, you should consider using the <xref:System.Text.RegularExpressions.Regex.Matches%2A> or <xref:System.String.IndexOf%2A> methods instead.</span></span> <span data-ttu-id="da6ad-107">Se tuttavia le prestazioni non rappresentano un problema critico o se la frase è già stata suddivisa per sottoporla ad altri tipi di query, anche LINQ costituisce una scelta appropriata per contare le parole o le frasi.</span><span class="sxs-lookup"><span data-stu-id="da6ad-107">However, if performance is not a critical issue, or you have already split the sentence in order to perform other types of queries over it, then it makes sense to use LINQ to count the words or phrases as well.</span></span>

## <a name="example"></a><span data-ttu-id="da6ad-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="da6ad-108">Example</span></span>

```vb
Class CountWords

    Shared Sub Main()

        Dim text As String = "Historically, the world of data and the world of objects" &
                  " have not been well integrated. Programmers work in C# or Visual Basic" &
                  " and also in SQL or XQuery. On the one side are concepts such as classes," &
                  " objects, fields, inheritance, and .NET Framework APIs. On the other side" &
                  " are tables, columns, rows, nodes, and separate languages for dealing with" &
                  " them. Data types often require translation between the two worlds; there are" &
                  " different standard functions. Because the object world has no notion of query, a" &
                  " query can only be represented as a string without compile-time type checking or" &
                  " IntelliSense support in the IDE. Transferring data from SQL tables or XML trees to" &
                  " objects in memory is often tedious and error-prone."

        Dim searchTerm As String = "data"

        ' Convert the string into an array of words.
        Dim dataSource As String() = text.Split(New Char() {" ", ",", ".", ";", ":"},
                                                 StringSplitOptions.RemoveEmptyEntries)

        ' Create and execute the query. It executes immediately
        ' because a singleton value is produced.
        ' Use ToLower to match "data" and "Data"
        Dim matchQuery = From word In dataSource
                      Where word.ToLowerInvariant() = searchTerm.ToLowerInvariant()
                      Select word

        ' Count the matches.
        Dim count As Integer = matchQuery.Count()
        Console.WriteLine(count & " occurrence(s) of the search term """ &
                          searchTerm & """ were found.")

        ' Keep console window open in debug mode.
        Console.WriteLine("Press any key to exit.")
        Console.ReadKey()
    End Sub
End Class
' Output:
' 3 occurrence(s) of the search term "data" were found.
```

## <a name="compile-the-code"></a><span data-ttu-id="da6ad-109">Compilare il codice</span><span class="sxs-lookup"><span data-stu-id="da6ad-109">Compile the code</span></span>

<span data-ttu-id="da6ad-110">Creare un progetto di applicazione console Visual Basic con un' `Imports` istruzione per lo spazio dei nomi System. Linq.</span><span class="sxs-lookup"><span data-stu-id="da6ad-110">Create a Visual Basic console application project, with an `Imports` statement for the System.Linq namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="da6ad-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da6ad-111">See also</span></span>

- <span data-ttu-id="da6ad-112">[LINQ and Strings (Visual Basic)](linq-and-strings.md) (LINQ e le stringhe (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="da6ad-112">[LINQ and Strings (Visual Basic)](linq-and-strings.md)</span></span>
