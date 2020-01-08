---
title: 'Procedura: eseguire una query per trovare i file duplicati in una struttura ad albero di directory (LINQ)'
ms.date: 07/20/2015
ms.assetid: 387d7c97-95dd-4a50-9761-7e9cf8ae9e6a
ms.openlocfilehash: 9870ccae327bccb0f6f93d49e3b2fc77d72f95cd
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75342177"
---
# <a name="how-to-query-for-duplicate-files-in-a-directory-tree-linq-visual-basic"></a><span data-ttu-id="840d2-102">Procedura: eseguire una query per File duplicati in un albero di directory (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="840d2-102">How to: Query for Duplicate Files in a Directory Tree (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="840d2-103">Talvolta i file con lo stesso nome possono trovarsi in più di una cartella.</span><span class="sxs-lookup"><span data-stu-id="840d2-103">Sometimes files that have the same name may be located in more than one folder.</span></span> <span data-ttu-id="840d2-104">Ad esempio, nella cartella di installazione di Visual Studio diverse cartelle hanno un file readme.htm.</span><span class="sxs-lookup"><span data-stu-id="840d2-104">For example, under the Visual Studio installation folder, several folders have a readme.htm file.</span></span> <span data-ttu-id="840d2-105">In questo esempio viene illustrato come eseguire una query per trovare tali nomi di file duplicati in una cartella radice specificata.</span><span class="sxs-lookup"><span data-stu-id="840d2-105">This example shows how to query for such duplicate file names under a specified root folder.</span></span> <span data-ttu-id="840d2-106">Nel secondo esempio viene illustrato come eseguire una query per trovare i file con dimensioni e ora di creazione corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="840d2-106">The second example shows how to query for files whose size and creation times also match.</span></span>  
  
## <a name="example"></a><span data-ttu-id="840d2-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="840d2-107">Example</span></span>  
  
```vb  
Module QueryDuplicateFileNames  
  
    Public Sub Main()  
  
        Dim path As String = "C:\Program Files\Microsoft Visual Studio 9.0\Common7"  
        QueryDuplicates1(path)  
        ' Uncomment to run this query instead  
        ' QueryDuplicates2(path)  
  
    End Sub  
    Sub QueryDuplicates1(ByVal root As String)  
        Dim dir As New System.IO.DirectoryInfo(root)  
        Dim duplicates = From aFile In dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories) _  
                                 Order By aFile.Name _  
                                 Group aFile By aFile.Name Into newGroup = Group _  
                                 Where newGroup.Count() >= 2 _  
                                 Select newGroup  
  
        ' Page the display so that the results can be read.  
        Dim trimLength = root.Length  
        PageOutput(duplicates, trimLength)  
  
    End Sub  
    Sub QueryDuplicates2(ByVal root As String)  
  
        ' This time a composite key is used. This sub finds all files  
        ' that have been copied into multiple subfolders.  
        Dim dir As New System.IO.DirectoryInfo(root)  
  
        Dim duplicates = From aFile In Dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories) _  
                                 Order By aFile.Name _  
                                 Group aFile By aFile.Name, aFile.CreationTime, aFile.Length Into newGroup = Group _  
                                 Where newGroup.Count() >= 2 _  
                                 Select newGroup  
  
        ' Page the display so that the results can be read.  
        Dim trimLength = root.Length  
        PageOutput(duplicates, trimLength)  
  
    End Sub  
    ' Pages console display for large query results. No more than one group per page.  
    ' This sub specifically works with group queries of FileInfo objects  
    ' but can be modified for any type.  
    Sub PageOutput(ByVal groupQuery, ByVal charsToSkip)  
  
        ' "3" = 1 line for extension key + 1 for "Press any key" + 1 for input cursor.  
        Dim numLines As Integer = Console.WindowHeight - 3  
        ' Flag to indicate whether there are more results to display  
        Dim goAgain As Boolean = True  
  
        For Each fg As IEnumerable(Of System.IO.FileInfo) In groupQuery  
            ' Start a new extension at the top of a page.  
            Dim currentLine As Integer = 0  
  
            Do While (currentLine < fg.Count())  
                Console.Clear()  
  
                ' Get the next page of results  
                ' No more than one filename per page  
                Dim resultPage = From file In fg _  
                                Skip currentLine Take numLines  
  
                ' Execute the query. Trim the paths in the output.  
                For Each line In resultPage  
                    Console.WriteLine(vbTab & line.FullName.Substring(charsToSkip))  
                Next  
  
                ' Advance the current position  
                currentLine = numLines + currentLine  
  
                ' Give the user a chance to break out of the loop  
                Console.WriteLine("Press any key for next page or the 'End' key to exit.")  
                Dim key As ConsoleKey = Console.ReadKey().Key  
                If key = ConsoleKey.End Then  
                    goAgain = False  
                    Exit For  
                End If  
            Loop  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="840d2-108">La prima query usa una chiave semplice per determinare una corrispondenza. Individua i file che hanno lo stesso nome ma contenuto diverso.</span><span class="sxs-lookup"><span data-stu-id="840d2-108">The first query uses a simple key to determine a match; this finds files that have the same name but whose contents might be different.</span></span> <span data-ttu-id="840d2-109">La seconda query usa una chiave composta per individuare la corrispondenza con tre proprietà dell'oggetto <xref:System.IO.FileInfo>.</span><span class="sxs-lookup"><span data-stu-id="840d2-109">The second query uses a compound key to match against three properties of the <xref:System.IO.FileInfo> object.</span></span> <span data-ttu-id="840d2-110">Questa query individuerà file che hanno lo stesso nome e contenuto simile o identico.</span><span class="sxs-lookup"><span data-stu-id="840d2-110">This query is much more likely to find files that have the same name and similar or identical content.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="840d2-111">Compilare il codice</span><span class="sxs-lookup"><span data-stu-id="840d2-111">Compile the code</span></span>  
<span data-ttu-id="840d2-112">Creare un progetto di applicazione console Visual Basic con un'istruzione `Imports` per lo spazio dei nomi System. Linq.</span><span class="sxs-lookup"><span data-stu-id="840d2-112">Create a Visual Basic console application project, with an `Imports` statement for the System.Linq namespace.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="840d2-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="840d2-113">See also</span></span>

- [<span data-ttu-id="840d2-114">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="840d2-114">LINQ to Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
- <span data-ttu-id="840d2-115">[LINQ and File Directories (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md) (LINQ e directory file (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="840d2-115">[LINQ and File Directories (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)</span></span>
