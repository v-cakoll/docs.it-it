---
title: 'Procedura: eseguire una Query per il numero totale di byte in un Set di cartelle (LINQ) (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: bfe85ed2-44dc-4ef1-aac7-241622b80a69
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: bda25acd3065898eeb61dce83d46d7526e825add
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq-visual-basic"></a><span data-ttu-id="e3baa-102">Procedura: eseguire una Query per il numero totale di byte in un Set di cartelle (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e3baa-102">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="e3baa-103">In questo esempio viene illustrato come recuperare il numero totale di byte utilizzati da tutti i file in una cartella specificata e tutte le relative sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="e3baa-103">This example shows how to retrieve the total number of bytes used by all the files in a specified folder and all its subfolders.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3baa-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="e3baa-104">Example</span></span>  
 <span data-ttu-id="e3baa-105">Il <xref:System.Linq.Enumerable.Sum%2A>metodo aggiunge i valori di tutti gli elementi selezionati nel `select` clausola.</xref:System.Linq.Enumerable.Sum%2A></span><span class="sxs-lookup"><span data-stu-id="e3baa-105">The <xref:System.Linq.Enumerable.Sum%2A> method adds the values of all the items selected in the `select` clause.</span></span> <span data-ttu-id="e3baa-106">È possibile modificare facilmente questa query per recuperare il file più grande o più piccolo nella struttura della directory specificata chiamando il <xref:System.Linq.Enumerable.Min%2A> <xref:System.Linq.Enumerable.Max%2A>metodo anziché <xref:System.Linq.Enumerable.Sum%2A>.</xref:System.Linq.Enumerable.Sum%2A> </xref:System.Linq.Enumerable.Max%2A> o</xref:System.Linq.Enumerable.Min%2A></span><span class="sxs-lookup"><span data-stu-id="e3baa-106">You can easily modify this query to retrieve the biggest or smallest file in the specified directory tree by calling the <xref:System.Linq.Enumerable.Min%2A> or <xref:System.Linq.Enumerable.Max%2A> method instead of <xref:System.Linq.Enumerable.Sum%2A>.</span></span>  
  
```vb  
Module QueryTotalBytes  
    Sub Main()  
  
        ' Change the drive\path if necessary.  
        Dim root As String = "C:\Program Files\Microsoft Visual Studio 9.0\VB"  
  
        'Take a snapshot of the folder contents.  
        ' This method assumes that the application has discovery permissions  
        ' for all folders under the specified path.  
        Dim fileList = My.Computer.FileSystem.GetFiles _  
                  (root, FileIO.SearchOption.SearchAllSubDirectories, "*.*")  
  
        Dim fileQuery = From file In fileList _  
                        Select GetFileLength(file)  
  
        ' Force execution and cache the results to avoid multiple trips to the file system.  
        Dim fileLengths = fileQuery.ToArray()  
  
        ' Find the largest file  
        Dim maxSize = Aggregate aFile In fileLengths Into Max()  
  
        ' Find the total number of bytes  
        Dim totalBytes = Aggregate aFile In fileLengths Into Sum()  
  
        Console.WriteLine("The largest file is " & maxSize & " bytes")  
        Console.WriteLine("There are " & totalBytes & " total bytes in " & _  
                          fileList.Count & " files under " & root)  
  
        ' Keep the console window open in debug mode  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
  
    ' This method is used to catch the possible exception  
    ' that can be raised when accessing the FileInfo.Length property.  
    Function GetFileLength(ByVal filename As String) As Long  
        Dim retval As Long  
        Try  
            Dim fi As New System.IO.FileInfo(filename)  
            retval = fi.Length  
        Catch ex As System.IO.FileNotFoundException  
            ' If a file is no longer present,  
            ' just return zero bytes.   
            retval = 0  
        End Try  
  
        Return retval  
    End Function  
End Module  
```  
  
 <span data-ttu-id="e3baa-107">Se è sufficiente contare il numero di byte in una struttura ad albero di directory specificata, è possibile farlo in modo più efficiente senza creare una query LINQ, che genera l'overhead della creazione della raccolta di elenco come origine dati.</span><span class="sxs-lookup"><span data-stu-id="e3baa-107">If you only have to count the number of bytes in a specified directory tree, you can do this more efficiently without creating a LINQ query, which incurs the overhead of creating the list collection as a data source.</span></span> <span data-ttu-id="e3baa-108">L'utilità dell'approccio LINQ aumenta se la query diventa più complessa, o quando è necessario eseguire più query sulla stessa origine dati.</span><span class="sxs-lookup"><span data-stu-id="e3baa-108">The usefulness of the LINQ approach increases as the query becomes more complex, or when you have to run multiple queries against the same data source.</span></span>  
  
 <span data-ttu-id="e3baa-109">La query effettua una chiamata a un metodo separato per ottenere la lunghezza del file.</span><span class="sxs-lookup"><span data-stu-id="e3baa-109">The query calls out to a separate method to obtain the file length.</span></span> <span data-ttu-id="e3baa-110">In tal modo di utilizzare la possibile eccezione generata se il file è stato eliminato in un altro thread dopo la <xref:System.IO.FileInfo>è stato creato l'oggetto nella chiamata a `GetFiles`.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="e3baa-110">It does this in order to consume the possible exception that will be raised if the file was deleted on another thread after the <xref:System.IO.FileInfo> object was created in the call to `GetFiles`.</span></span> <span data-ttu-id="e3baa-111">Anche se il <xref:System.IO.FileInfo>oggetto è già stato creato, l'eccezione può verificarsi perché un <xref:System.IO.FileInfo>oggetto tenta di aggiornare il relativo <xref:System.IO.FileInfo.Length%2A>proprietà con la lunghezza più recente la prima volta che si accede alla proprietà.</xref:System.IO.FileInfo.Length%2A> </xref:System.IO.FileInfo> </xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="e3baa-111">Even though the <xref:System.IO.FileInfo> object has already been created, the exception can occur because a <xref:System.IO.FileInfo> object will try to refresh its <xref:System.IO.FileInfo.Length%2A> property with the most current length the first time the property is accessed.</span></span> <span data-ttu-id="e3baa-112">Inserendo questa operazione in un blocco try-catch all'esterno della query, il codice segue la regola di evitare operazioni di query che possono causare effetti collaterali.</span><span class="sxs-lookup"><span data-stu-id="e3baa-112">By putting this operation in a try-catch block outside the query, the code follows the rule of avoiding operations in queries that can cause side-effects.</span></span> <span data-ttu-id="e3baa-113">In generale, è necessario prestare particolare attenzione quando si usano le eccezioni per assicurarsi che un'applicazione non viene lasciata in uno stato sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="e3baa-113">In general, great care must be taken when you consume exceptions to make sure that an application is not left in an unknown state.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e3baa-114">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="e3baa-114">Compiling the Code</span></span>  
 <span data-ttu-id="e3baa-115">Creare un progetto destinato a .NET Framework versione 3.5 o versione successiva con un riferimento a System.Core.dll e una `Imports` istruzione per lo spazio dei nomi System. Linq.</span><span class="sxs-lookup"><span data-stu-id="e3baa-115">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a   `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3baa-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3baa-116">See Also</span></span>  
 <span data-ttu-id="e3baa-117">[LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) </span><span class="sxs-lookup"><span data-stu-id="e3baa-117">[LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) </span></span>  
<span data-ttu-id="e3baa-118"> [Directory di File (Visual Basic) e LINQ](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)</span><span class="sxs-lookup"><span data-stu-id="e3baa-118"> [LINQ and File Directories (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)</span></span>
