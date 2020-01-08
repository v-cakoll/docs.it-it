---
title: 'Procedura: ordinare o filtrare i dati di testo in base a qualsiasi parola o campo (LINQ)'
ms.date: 07/20/2015
ms.assetid: 9df137fe-335b-46e0-aecf-ea8a9eddd4e3
ms.openlocfilehash: f0eeda77a721d482ec7a2b8562c0a71f34c5a3ae
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348040"
---
# <a name="how-to-sort-or-filter-text-data-by-any-word-or-field-linq-visual-basic"></a><span data-ttu-id="7a972-102">Procedura: ordinare o filtrare i dati di testo in base a qualsiasi parola o campo (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7a972-102">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>

<span data-ttu-id="7a972-103">L'esempio seguente illustra come ordinare righe di testo strutturato, ad esempio valori delimitati da virgole, in base a un qualsiasi campo.</span><span class="sxs-lookup"><span data-stu-id="7a972-103">The following example shows how to sort lines of structured text, such as comma-separated values, by any field in the line.</span></span> <span data-ttu-id="7a972-104">Il campo può essere specificato in modo dinamico in runtime.</span><span class="sxs-lookup"><span data-stu-id="7a972-104">The field may be dynamically specified at runtime.</span></span> <span data-ttu-id="7a972-105">Si supponga che i campi in scores.csv rappresentino il numero ID di uno studente, seguito da una serie di quattro punteggi di test.</span><span class="sxs-lookup"><span data-stu-id="7a972-105">Assume that the fields in scores.csv represent a student's ID number, followed by a series of four test scores.</span></span>

### <a name="to-create-a-file-that-contains-data"></a><span data-ttu-id="7a972-106">Per creare un file che contenga i dati</span><span class="sxs-lookup"><span data-stu-id="7a972-106">To create a file that contains data</span></span>

<span data-ttu-id="7a972-107">Copiare i dati scores. csv dall'argomento [procedura: aggiungere contenuto da file non analoghi (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md) e salvarlo nella cartella della soluzione.</span><span class="sxs-lookup"><span data-stu-id="7a972-107">Copy the scores.csv data from the topic [How to: Join Content from Dissimilar Files (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md) and save it to your solution folder.</span></span>

## <a name="example"></a><span data-ttu-id="7a972-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="7a972-108">Example</span></span>

```vb
Class SortLines

    Shared Sub Main()
        Dim scores As String() = System.IO.File.ReadAllLines("../../../scores.csv")

        ' Change this to any value from 0 to 4
        Dim sortField As Integer = 1

        Console.WriteLine("Sorted highest to lowest by field " & sortField)

        ' Demonstrates how to return query from a method.
        ' The query is executed here.
        For Each str As String In SortQuery(scores, sortField)
            Console.WriteLine(str)
        Next

        ' Keep console window open in debug mode.
        Console.WriteLine("Press any key to exit.")
        Console.ReadKey()

    End Sub

    Shared Function SortQuery(
        ByVal source As IEnumerable(Of String),
        ByVal num As Integer) As IEnumerable(Of String)

        Dim scoreQuery = From line In source
                         Let fields = line.Split(New Char() {","})
                         Order By fields(num) Descending
                         Select line

        Return scoreQuery
    End Function
End Class
' Output:
' Sorted highest to lowest by field 1
' 116, 99, 86, 90, 94
' 120, 99, 82, 81, 79
' 111, 97, 92, 81, 60
' 114, 97, 89, 85, 82
' 121, 96, 85, 91, 60
' 122, 94, 92, 91, 91
' 117, 93, 92, 80, 87
' 118, 92, 90, 83, 78
' 113, 88, 94, 65, 91
' 112, 75, 84, 91, 39
' 119, 68, 79, 88, 92
' 115, 35, 72, 91, 70
```

<span data-ttu-id="7a972-109">Questo esempio illustra anche come restituire una variabile di query da una funzione.</span><span class="sxs-lookup"><span data-stu-id="7a972-109">This example also demonstrates how to return a query variable from a Function.</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="7a972-110">Compilare il codice</span><span class="sxs-lookup"><span data-stu-id="7a972-110">Compile the code</span></span>

<span data-ttu-id="7a972-111">Creare un progetto di applicazione console Visual Basic con un'istruzione `Imports` per lo spazio dei nomi System. Linq.</span><span class="sxs-lookup"><span data-stu-id="7a972-111">Create a Visual Basic console application project, with an `Imports` statement for the System.Linq namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="7a972-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a972-112">See also</span></span>

- [<span data-ttu-id="7a972-113">LINQ e stringhe (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7a972-113">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
