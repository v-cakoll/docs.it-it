---
title: Come combinare query LINQ con espressioni regolari
ms.date: 07/20/2015
ms.assetid: 3da1bd10-b0d8-4d5b-a637-966891c13592
ms.openlocfilehash: a091418be1f7cc30d42a98f80ebae2d36d29b5d8
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337554"
---
# <a name="how-to-combine-linq-queries-with-regular-expressions-visual-basic"></a><span data-ttu-id="2895f-102">Come combinare query LINQ con espressioni regolari (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2895f-102">How to combine LINQ queries with regular expressions (Visual Basic)</span></span>

<span data-ttu-id="2895f-103">In questo esempio viene illustrato come usare la classe <xref:System.Text.RegularExpressions.Regex> per creare un'espressione regolare per una corrispondenza più complessa nelle stringhe di testo.</span><span class="sxs-lookup"><span data-stu-id="2895f-103">This example shows how to use the <xref:System.Text.RegularExpressions.Regex> class to create a regular expression for more complex matching in text strings.</span></span> <span data-ttu-id="2895f-104">La query LINQ consente di filtrare esattamente i file che si vuole cercare tramite l'espressione regolare e di dare forma ai risultati.</span><span class="sxs-lookup"><span data-stu-id="2895f-104">The LINQ query makes it easy to filter on exactly the files that you want to search with the regular expression, and to shape the results.</span></span>

## <a name="example"></a><span data-ttu-id="2895f-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="2895f-105">Example</span></span>

```vb
Imports System.IO
Imports System.Text.RegularExpressions

Class LinqRegExVB

    Shared Sub Main()

        ' Root folder to query, along with all subfolders.
        ' Modify this path as necessary so that it accesses your Visual Studio folder.
        Dim startFolder As String = "C:\Program Files (x86)\Microsoft Visual Studio 14.0\"
        ' One of the following paths may be more appropriate on your computer.
        'Dim startFolder As String = "C:\Program Files (x86)\Microsoft Visual Studio\2017\"

        ' Take a snapshot of the file system.
        Dim fileList As IEnumerable(Of FileInfo) = GetFiles(startFolder)

        ' Create a regular expression to find all things "Visual".
        Dim searchTerm As New Regex("Visual (Basic|C#|C\+\+|Studio)")

        ' Search the contents of each .htm file.
        ' Remove the where clause to find even more matches!
        ' This query produces a list of files where a match
        ' was found, and a list of the matches in that file.
        ' Note: Explicit typing of "Match" in select clause.
        ' This is required because MatchCollection is not a
        ' generic IEnumerable collection.
        Dim queryMatchingFiles = From afile In fileList
                                Where afile.Extension = ".htm"
                                Let fileText = File.ReadAllText(afile.FullName)
                                Let matches = searchTerm.Matches(fileText)
                                Where (matches.Count > 0)
                                Select Name = afile.FullName,
                                       Matches = From match As Match In matches
                                                 Select match.Value

        ' Execute the query.
        Console.WriteLine("The term " & searchTerm.ToString() & " was found in:")

        For Each fileMatches In queryMatchingFiles
            ' Trim the path a bit, then write
            ' the file name in which a match was found.
            Dim s = fileMatches.Name.Substring(startFolder.Length - 1)
            Console.WriteLine(s)

            ' For this file, write out all the matching strings
            For Each match In fileMatches.Matches
                Console.WriteLine("  " + match)
            Next
        Next

        ' Keep the console window open in debug mode
        Console.WriteLine("Press any key to exit")
        Console.ReadKey()
    End Sub

    ' Function to retrieve a list of files. Note that this is a copy
    ' of the file information.
    Shared Function GetFiles(root As String) As IEnumerable(Of FileInfo)
        Return From file In My.Computer.FileSystem.GetFiles(
                   root, FileIO.SearchOption.SearchAllSubDirectories, "*.*")
               Select New FileInfo(file)
    End Function

End Class
```

<span data-ttu-id="2895f-106">Si noti che è anche possibile eseguire una query sull'oggetto <xref:System.Text.RegularExpressions.MatchCollection> restituito da una ricerca `RegEx`.</span><span class="sxs-lookup"><span data-stu-id="2895f-106">Note that you can also query the <xref:System.Text.RegularExpressions.MatchCollection> object that is returned by a `RegEx` search.</span></span> <span data-ttu-id="2895f-107">In questo esempio viene generato nei risultati solo il valore di ogni corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="2895f-107">In this example only the value of each match is produced in the results.</span></span> <span data-ttu-id="2895f-108">Tuttavia, è anche possibile usare LINQ per eseguire tutti i tipi di filtro, ordinamento e raggruppamento sulla raccolta.</span><span class="sxs-lookup"><span data-stu-id="2895f-108">However, it is also possible to use LINQ to perform all kinds of filtering, sorting, and grouping on that collection.</span></span> <span data-ttu-id="2895f-109">Poiché <xref:System.Text.RegularExpressions.MatchCollection> è una raccolta non generica <xref:System.Collections.IEnumerable>, è necessario dichiarare esplicitamente il tipo della variabile di intervallo nella query.</span><span class="sxs-lookup"><span data-stu-id="2895f-109">Because <xref:System.Text.RegularExpressions.MatchCollection> is a non-generic <xref:System.Collections.IEnumerable> collection, you have to explicitly state the type of the range variable in the query.</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="2895f-110">Compilare il codice</span><span class="sxs-lookup"><span data-stu-id="2895f-110">Compile the code</span></span>

<span data-ttu-id="2895f-111">Creare un progetto di applicazione console Visual Basic, copiare e incollare l'esempio di codice e modificare il valore dell'oggetto di avvio nelle proprietà del progetto.</span><span class="sxs-lookup"><span data-stu-id="2895f-111">Create a Visual Basic console application project, copy and paste the code sample, and adjust the Startup object value in the project properties.</span></span>

## <a name="see-also"></a><span data-ttu-id="2895f-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2895f-112">See also</span></span>

- [<span data-ttu-id="2895f-113">LINQ e stringhe (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2895f-113">LINQ and Strings (Visual Basic)</span></span>](linq-and-strings.md)
- <span data-ttu-id="2895f-114">[LINQ and File Directories (Visual Basic)](linq-and-file-directories.md) (LINQ e directory file (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="2895f-114">[LINQ and File Directories (Visual Basic)](linq-and-file-directories.md)</span></span>
