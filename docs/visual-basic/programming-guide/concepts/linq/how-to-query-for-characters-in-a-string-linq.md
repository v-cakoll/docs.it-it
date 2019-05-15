---
title: 'Procedura: Query per trovare caratteri in una stringa (LINQ) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 499ebbe0-746c-4235-9dba-ce722c12b50e
ms.openlocfilehash: fba5d8ca6c0c060c76b1ecf4f66434ce0884e733
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65593312"
---
# <a name="how-to-query-for-characters-in-a-string-linq-visual-basic"></a><span data-ttu-id="2923f-102">Procedura: Query per trovare caratteri in una stringa (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2923f-102">How to: Query for Characters in a String (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="2923f-103">Poiché la classe <xref:System.String> implementa l'interfaccia generica <xref:System.Collections.Generic.IEnumerable%601>, è possibile eseguire una query su qualsiasi stringa come una sequenza di caratteri.</span><span class="sxs-lookup"><span data-stu-id="2923f-103">Because the <xref:System.String> class implements the generic <xref:System.Collections.Generic.IEnumerable%601> interface, any string can be queried as a sequence of characters.</span></span> <span data-ttu-id="2923f-104">Tuttavia, questo uso di LINQ non è comune.</span><span class="sxs-lookup"><span data-stu-id="2923f-104">However, this is not a common use of LINQ.</span></span> <span data-ttu-id="2923f-105">Per le operazioni con criteri di ricerca complessi, usare la classe <xref:System.Text.RegularExpressions.Regex>.</span><span class="sxs-lookup"><span data-stu-id="2923f-105">For complex pattern matching operations, use the <xref:System.Text.RegularExpressions.Regex> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2923f-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="2923f-106">Example</span></span>  
 <span data-ttu-id="2923f-107">Nell'esempio seguente viene eseguita una query su una stringa per determinare il numero di cifre che contiene.</span><span class="sxs-lookup"><span data-stu-id="2923f-107">The following example queries a string to determine the number of numeric digits it contains.</span></span> <span data-ttu-id="2923f-108">Si noti che, dopo la prima esecuzione, la query viene "riutilizzata".</span><span class="sxs-lookup"><span data-stu-id="2923f-108">Note that the query is "reused" after it is executed the first time.</span></span> <span data-ttu-id="2923f-109">Ciò è possibile perché la query stessa non archivia i risultati effettivi.</span><span class="sxs-lookup"><span data-stu-id="2923f-109">This is possible because the query itself does not store any actual results.</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="2923f-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="2923f-110">Compiling the Code</span></span>  
<span data-ttu-id="2923f-111">Creare un progetto di applicazione console VB.NET, con un `Imports` istruzione dello spazio dei nomi System. Linq.</span><span class="sxs-lookup"><span data-stu-id="2923f-111">Create a VB.NET console application project, with an `Imports` statement for the System.Linq namespace.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2923f-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2923f-112">See also</span></span>

- [<span data-ttu-id="2923f-113">LINQ e stringhe (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2923f-113">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
- [<span data-ttu-id="2923f-114">Procedura: Combinare query LINQ con espressioni regolari (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2923f-114">How to: Combine LINQ Queries with Regular Expressions (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md)
