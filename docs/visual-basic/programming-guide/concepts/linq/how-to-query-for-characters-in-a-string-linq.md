---
title: 'Procedura: eseguire una query per trovare caratteri in una stringa (LINQ)'
ms.date: 07/20/2015
ms.assetid: 499ebbe0-746c-4235-9dba-ce722c12b50e
ms.openlocfilehash: 9da6d5abd6155a7af5ec59e17693e8acae7e7b73
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347714"
---
# <a name="how-to-query-for-characters-in-a-string-linq-visual-basic"></a><span data-ttu-id="00906-102">How to: Query for Characters in a String (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00906-102">How to: Query for Characters in a String (LINQ) (Visual Basic)</span></span>

<span data-ttu-id="00906-103">Poiché la classe <xref:System.String> implementa l'interfaccia generica <xref:System.Collections.Generic.IEnumerable%601>, è possibile eseguire una query su qualsiasi stringa come una sequenza di caratteri.</span><span class="sxs-lookup"><span data-stu-id="00906-103">Because the <xref:System.String> class implements the generic <xref:System.Collections.Generic.IEnumerable%601> interface, any string can be queried as a sequence of characters.</span></span> <span data-ttu-id="00906-104">Tuttavia, questo uso di LINQ non è comune.</span><span class="sxs-lookup"><span data-stu-id="00906-104">However, this is not a common use of LINQ.</span></span> <span data-ttu-id="00906-105">Per le operazioni con criteri di ricerca complessi, usare la classe <xref:System.Text.RegularExpressions.Regex>.</span><span class="sxs-lookup"><span data-stu-id="00906-105">For complex pattern matching operations, use the <xref:System.Text.RegularExpressions.Regex> class.</span></span>

## <a name="example"></a><span data-ttu-id="00906-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="00906-106">Example</span></span>

<span data-ttu-id="00906-107">Nell'esempio seguente viene eseguita una query su una stringa per determinare il numero di cifre che contiene.</span><span class="sxs-lookup"><span data-stu-id="00906-107">The following example queries a string to determine the number of numeric digits it contains.</span></span> <span data-ttu-id="00906-108">Si noti che, dopo la prima esecuzione, la query viene "riutilizzata".</span><span class="sxs-lookup"><span data-stu-id="00906-108">Note that the query is "reused" after it is executed the first time.</span></span> <span data-ttu-id="00906-109">Ciò è possibile perché la query stessa non archivia i risultati effettivi.</span><span class="sxs-lookup"><span data-stu-id="00906-109">This is possible because the query itself does not store any actual results.</span></span>

```vb
Class QueryAString

    Shared Sub Main()

        ' A string is an IEnumerable data source.
        Dim aString As String = "ABCDE99F-J74-12-89A"

        ' Select only those characters that are numbers
        Dim stringQuery = From ch In aString
                          Where Char.IsDigit(ch)
                          Select ch
        ' Execute the query
        For Each c As Char In stringQuery
            Console.Write(c & " ")
        Next

        ' Call the Count method on the existing query.
        Dim count As Integer = stringQuery.Count()
        Console.WriteLine(System.Environment.NewLine & "Count = " & count)

        ' Select all characters before the first '-'
        Dim stringQuery2 = aString.TakeWhile(Function(c) c <> "-")

        ' Execute the second query
        For Each ch In stringQuery2
            Console.Write(ch)
        Next

        Console.WriteLine(System.Environment.NewLine & "Press any key to exit")
        Console.ReadKey()
    End Sub
End Class
' Output:
' 9 9 7 4 1 2 8 9
' Count = 8
' ABCDE99F
```

## <a name="compiling-the-code"></a><span data-ttu-id="00906-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="00906-110">Compiling the Code</span></span>

<span data-ttu-id="00906-111">Create a VB.NET console application project, with an `Imports` statement for the System.Linq namespace.</span><span class="sxs-lookup"><span data-stu-id="00906-111">Create a VB.NET console application project, with an `Imports` statement for the System.Linq namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="00906-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00906-112">See also</span></span>

- [<span data-ttu-id="00906-113">LINQ and Strings (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00906-113">LINQ and Strings (Visual Basic)</span></span>](linq-and-strings.md)
- [<span data-ttu-id="00906-114">How to combine LINQ queries with regular expressions (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00906-114">How to combine LINQ queries with regular expressions (Visual Basic)</span></span>](how-to-combine-linq-queries-with-regular-expressions.md)
