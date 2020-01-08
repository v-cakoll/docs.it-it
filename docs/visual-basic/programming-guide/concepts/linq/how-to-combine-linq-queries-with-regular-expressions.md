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
# <a name="how-to-combine-linq-queries-with-regular-expressions-visual-basic"></a>Come combinare query LINQ con espressioni regolari (Visual Basic)

In questo esempio viene illustrato come usare la classe <xref:System.Text.RegularExpressions.Regex> per creare un'espressione regolare per una corrispondenza più complessa nelle stringhe di testo. La query LINQ consente di filtrare esattamente i file che si vuole cercare tramite l'espressione regolare e di dare forma ai risultati.

## <a name="example"></a>Esempio

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

Si noti che è anche possibile eseguire una query sull'oggetto <xref:System.Text.RegularExpressions.MatchCollection> restituito da una ricerca `RegEx`. In questo esempio viene generato nei risultati solo il valore di ogni corrispondenza. Tuttavia, è anche possibile usare LINQ per eseguire tutti i tipi di filtro, ordinamento e raggruppamento sulla raccolta. Poiché <xref:System.Text.RegularExpressions.MatchCollection> è una raccolta non generica <xref:System.Collections.IEnumerable>, è necessario dichiarare esplicitamente il tipo della variabile di intervallo nella query.

## <a name="compile-the-code"></a>Compilare il codice

Creare un progetto di applicazione console Visual Basic, copiare e incollare l'esempio di codice e modificare il valore dell'oggetto di avvio nelle proprietà del progetto.

## <a name="see-also"></a>Vedere anche

- [LINQ e stringhe (Visual Basic)](linq-and-strings.md)
- [LINQ and File Directories (Visual Basic)](linq-and-file-directories.md) (LINQ e directory file (Visual Basic))
