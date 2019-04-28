---
title: 'Procedura: Eseguire query sul contenuto dei file in una cartella (LINQ) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: edacbcd3-f3e4-4429-a8be-28a58dc0dd70
ms.openlocfilehash: 04909de9fe3898600b127f1f7a5ba46834bc239a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61794719"
---
# <a name="how-to-query-the-contents-of-files-in-a-folder-linq-visual-basic"></a><span data-ttu-id="55aa6-102">Procedura: Eseguire query sul contenuto dei file in una cartella (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55aa6-102">How to: Query the Contents of Files in a Folder (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="55aa6-103">Questo esempio illustra come eseguire una query su tutti i file in un albero di directory specificato, aprire ogni file e controllarne il contenuto.</span><span class="sxs-lookup"><span data-stu-id="55aa6-103">This example shows how to query over all the files in a specified directory tree, open each file, and inspect its contents.</span></span> <span data-ttu-id="55aa6-104">Questo tipo di tecnica può essere usato per creare indici o indici inversi del contenuto di un albero di directory.</span><span class="sxs-lookup"><span data-stu-id="55aa6-104">This type of technique could be used to create indexes or reverse indexes of the contents of a directory tree.</span></span> <span data-ttu-id="55aa6-105">In questo esempio viene eseguita una semplice ricerca di una stringa.</span><span class="sxs-lookup"><span data-stu-id="55aa6-105">A simple string search is performed in this example.</span></span> <span data-ttu-id="55aa6-106">Tuttavia, con un'espressione regolare è possibile eseguire tipi di criteri di ricerca più complessi.</span><span class="sxs-lookup"><span data-stu-id="55aa6-106">However, more complex types of pattern matching can be performed with a regular expression.</span></span> <span data-ttu-id="55aa6-107">Per altre informazioni, vedere [Procedura: Combinare query LINQ con espressioni regolari (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="55aa6-107">For more information, see [How to: Combine LINQ Queries with Regular Expressions (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="55aa6-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="55aa6-108">Example</span></span>  
  
```vb  
Module Module1  
    'QueryContents  
    Public Sub Main()  
  
        ' Modify this path as necessary.  
        Dim startFolder = "c:\program files\Microsoft Visual Studio 9.0\VB\"  
  
        'Take a snapshot of the folder contents  
        Dim dir As New System.IO.DirectoryInfo(startFolder)  
        Dim fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories)  
  
        Dim searchTerm = "Visual Studio"  
  
        ' Search the contents of each file.  
        ' A regular expression created with the RegEx class  
        ' could be used instead of the Contains method.  
        Dim queryMatchingFiles = From file In fileList _  
                                 Where file.Extension = ".htm" _  
                                 Let fileText = GetFileText(file.FullName) _  
                                 Where fileText.Contains(searchTerm) _  
                                 Select file.FullName  
  
        Console.WriteLine("The term " & searchTerm & " was found in:")  
  
        ' Execute the query.  
        For Each filename In queryMatchingFiles  
            Console.WriteLine(filename)  
        Next  
  
        ' Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit")  
        Console.ReadKey()  
  
    End Sub  
  
    ' Read the contents of the file. This is done in a separate  
    ' function in order to handle potential file system errors.  
    Function GetFileText(ByVal name As String) As String  
  
        ' If the file has been deleted, the right thing  
        ' to do in this case is return an empty string.  
        Dim fileContents = String.Empty  
  
        ' If the file has been deleted since we took   
        ' the snapshot, ignore it and return the empty string.  
        If System.IO.File.Exists(name) Then  
            fileContents = System.IO.File.ReadAllText(name)  
        End If  
  
        Return fileContents  
  
    End Function  
End Module  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="55aa6-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="55aa6-109">Compiling the Code</span></span>  
 <span data-ttu-id="55aa6-110">Creare un progetto che usi .NET Framework versione 3.5 o successiva con un riferimento a System.Core.dll e un'istruzione `Imports` per lo spazio dei nomi System.Linq.</span><span class="sxs-lookup"><span data-stu-id="55aa6-110">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55aa6-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55aa6-111">See also</span></span>

- [<span data-ttu-id="55aa6-112">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55aa6-112">LINQ to Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
- <span data-ttu-id="55aa6-113">[LINQ and File Directories (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md) (LINQ e directory file (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="55aa6-113">[LINQ and File Directories (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)</span></span>
