---
title: 'Procedura: eseguire una query per trovare caratteri in una stringa (LINQ)'
ms.date: 07/20/2015
ms.assetid: 499ebbe0-746c-4235-9dba-ce722c12b50e
ms.openlocfilehash: 2f306a488610aaa5775210eba3d7312b092545a7
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345518"
---
# <a name="how-to-query-for-characters-in-a-string-linq-visual-basic"></a><span data-ttu-id="c43f1-102">Procedura: eseguire una query per i caratteri in una stringa (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c43f1-102">How to: Query for Characters in a String (LINQ) (Visual Basic)</span></span>

<span data-ttu-id="c43f1-103">Poiché la classe <xref:System.String> implementa l'interfaccia generica <xref:System.Collections.Generic.IEnumerable%601>, è possibile eseguire una query su qualsiasi stringa come una sequenza di caratteri.</span><span class="sxs-lookup"><span data-stu-id="c43f1-103">Because the <xref:System.String> class implements the generic <xref:System.Collections.Generic.IEnumerable%601> interface, any string can be queried as a sequence of characters.</span></span> <span data-ttu-id="c43f1-104">Tuttavia, questo uso di LINQ non è comune.</span><span class="sxs-lookup"><span data-stu-id="c43f1-104">However, this is not a common use of LINQ.</span></span> <span data-ttu-id="c43f1-105">Per le operazioni con criteri di ricerca complessi, usare la classe <xref:System.Text.RegularExpressions.Regex>.</span><span class="sxs-lookup"><span data-stu-id="c43f1-105">For complex pattern matching operations, use the <xref:System.Text.RegularExpressions.Regex> class.</span></span>

## <a name="example"></a><span data-ttu-id="c43f1-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="c43f1-106">Example</span></span>

<span data-ttu-id="c43f1-107">Nell'esempio seguente viene eseguita una query su una stringa per determinare il numero di cifre che contiene.</span><span class="sxs-lookup"><span data-stu-id="c43f1-107">The following example queries a string to determine the number of numeric digits it contains.</span></span> <span data-ttu-id="c43f1-108">Si noti che, dopo la prima esecuzione, la query viene "riutilizzata".</span><span class="sxs-lookup"><span data-stu-id="c43f1-108">Note that the query is "reused" after it is executed the first time.</span></span> <span data-ttu-id="c43f1-109">Ciò è possibile perché la query stessa non archivia i risultati effettivi.</span><span class="sxs-lookup"><span data-stu-id="c43f1-109">This is possible because the query itself does not store any actual results.</span></span>

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

## <a name="compile-the-code"></a><span data-ttu-id="c43f1-110">Compilare il codice</span><span class="sxs-lookup"><span data-stu-id="c43f1-110">Compile the code</span></span>

<span data-ttu-id="c43f1-111">Creare un progetto di applicazione console Visual Basic con un'istruzione `Imports` per lo spazio dei nomi System. Linq.</span><span class="sxs-lookup"><span data-stu-id="c43f1-111">Create a Visual Basic console application project, with an `Imports` statement for the System.Linq namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="c43f1-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c43f1-112">See also</span></span>

- [<span data-ttu-id="c43f1-113">LINQ e stringhe (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c43f1-113">LINQ and Strings (Visual Basic)</span></span>](linq-and-strings.md)
- [<span data-ttu-id="c43f1-114">Come combinare query LINQ con espressioni regolari (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c43f1-114">How to combine LINQ queries with regular expressions (Visual Basic)</span></span>](how-to-combine-linq-queries-with-regular-expressions.md)
