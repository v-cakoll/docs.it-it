---
title: "Procedura: eseguire una Query per il più grande o più file in una struttura di Directory (LINQ) (Visual Basic) | Documenti di Microsoft"
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
ms.assetid: 8c1c9f0c-95dd-4222-9be2-9ec026a13e81
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
ms.openlocfilehash: 95c5197b2cb66745201ceac89b78fe67b95ecb75
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq-visual-basic"></a><span data-ttu-id="1eab6-102">Procedura: eseguire una query per trovare il file o i file più grandi in un albero di directory (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1eab6-102">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="1eab6-103">Questo esempio mostra cinque query relative alle dimensioni del file in byte:</span><span class="sxs-lookup"><span data-stu-id="1eab6-103">This example shows five queries related to file size in bytes:</span></span>  
  
-   <span data-ttu-id="1eab6-104">Come recuperare la dimensione in byte del file più grande.</span><span class="sxs-lookup"><span data-stu-id="1eab6-104">How to retrieve the size in bytes of the largest file.</span></span>  
  
-   <span data-ttu-id="1eab6-105">Come recuperare la dimensione in byte del file più piccolo.</span><span class="sxs-lookup"><span data-stu-id="1eab6-105">How to retrieve the size in bytes of the smallest file.</span></span>  
  
-   <span data-ttu-id="1eab6-106">Come recuperare il <xref:System.IO.FileInfo>file più grande o più piccolo dell'oggetto da uno o più cartelle in una cartella radice specificata.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="1eab6-106">How to retrieve the <xref:System.IO.FileInfo> object largest or smallest file from one or more folders under a specified root folder.</span></span>  
  
-   <span data-ttu-id="1eab6-107">Come recuperare una sequenza, ad esempio i file di dimensioni maggiori di 10.</span><span class="sxs-lookup"><span data-stu-id="1eab6-107">How to retrieve a sequence such as the 10 largest files.</span></span>  
  
-   <span data-ttu-id="1eab6-108">Come ordinare i file in gruppi in base alle dimensioni in byte, ignorando i file che sono minori dimensioni specificate.</span><span class="sxs-lookup"><span data-stu-id="1eab6-108">How to order files into groups based on their file size in bytes, ignoring files that are less than a specified size.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1eab6-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="1eab6-109">Example</span></span>  
 <span data-ttu-id="1eab6-110">Nell'esempio seguente contiene cinque query distinte che illustrano come eseguire una query e i file di gruppo, in base alle dimensioni in byte.</span><span class="sxs-lookup"><span data-stu-id="1eab6-110">The following example contains five separate queries that show how to query and group files, depending on their file size in bytes.</span></span> <span data-ttu-id="1eab6-111">È possibile modificare con facilità questi esempi per basare la query su un'altra proprietà del <xref:System.IO.FileInfo>oggetto.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="1eab6-111">You can easily modify these examples to base the query on some other property of the <xref:System.IO.FileInfo> object.</span></span>  
  
```vb  
Module QueryBySize  
    Sub Main()  
  
        ' Change the drive\path if necessary  
        Dim root As String = "C:\Program Files\Microsoft Visual Studio 9.0"  
  
        'Take a snapshot of the folder contents  
        Dim dir As New System.IO.DirectoryInfo(root)  
        Dim fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories)  
  
        ' Return the size of the largest file  
        Dim maxSize = Aggregate aFile In fileList Into Max(GetFileLength(aFile))  
  
        'Dim maxSize = fileLengths.Max  
        Console.WriteLine("The length of the largest file under {0} is {1}", _  
                          root, maxSize)  
  
        ' Return the FileInfo object of the largest file  
        ' by sorting and selecting from the beginning of the list  
        Dim filesByLengDesc = From file In fileList _  
                              Let filelength = GetFileLength(file) _  
                              Where filelength > 0 _  
                              Order By filelength Descending _  
                              Select file  
  
        Dim longestFile = filesByLengDesc.First  
  
        Console.WriteLine("The largest file under {0} is {1} with a length of {2} bytes", _  
                          root, longestFile.FullName, longestFile.Length)  
  
        Dim smallestFile = filesByLengDesc.Last  
  
        Console.WriteLine("The smallest file under {0} is {1} with a length of {2} bytes", _  
                                root, smallestFile.FullName, smallestFile.Length)  
  
        ' Return the FileInfos for the 10 largest files  
        ' Based on a previous query, but nothing is executed  
        ' until the For Each statement below.  
        Dim tenLargest = From file In filesByLengDesc Take 10  
  
        Console.WriteLine("The 10 largest files under {0} are:", root)  
  
        For Each fi As System.IO.FileInfo In tenLargest  
            Console.WriteLine("{0}: {1} bytes", fi.FullName, fi.Length)  
        Next  
  
        ' Group files according to their size,  
        ' leaving out the ones under 200K  
        Dim sizeGroups = From file As System.IO.FileInfo In fileList _  
                         Where file.Length > 0 _  
                         Let groupLength = file.Length / 100000 _  
                         Group file By groupLength Into fileGroup = Group _  
                         Where groupLength >= 2 _  
                         Order By groupLength Descending  
  
        For Each group In sizeGroups  
            Console.WriteLine(group.groupLength + "00000")  
  
            For Each item As System.IO.FileInfo In group.fileGroup  
                Console.WriteLine("   {0}: {1}", item.Name, item.Length)  
            Next  
        Next  
  
        ' Keep the console window open in debug mode  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
  
    End Sub  
  
    ' This method is used to catch the possible exception  
    ' that can be raised when accessing the FileInfo.Length property.  
    ' In this particular case, it is safe to ignore the exception.  
    Function GetFileLength(ByVal fi As System.IO.FileInfo) As Long  
        Dim retval As Long  
        Try  
            retval = fi.Length  
        Catch ex As FileNotFoundException  
            ' If a file is no longer present,  
            ' just return zero bytes.   
            retval = 0  
        End Try  
  
        Return retval  
    End Function  
End Module  
```  
  
 <span data-ttu-id="1eab6-112">Per restituire uno o più completare <xref:System.IO.FileInfo>oggetti, la query deve prima esaminare ciascuno di essi nei dati di origine e poi ordinarli in base al valore della proprietà Length.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="1eab6-112">To return one or more complete <xref:System.IO.FileInfo> objects, the query first must examine each one in the data source, and then sort them by the value of their Length property.</span></span> <span data-ttu-id="1eab6-113">Può quindi restituire il singolo oggetto o la sequenza con le lunghezze maggiori.</span><span class="sxs-lookup"><span data-stu-id="1eab6-113">Then it can return the single one or the sequence with the greatest lengths.</span></span> <span data-ttu-id="1eab6-114">Utilizzare <xref:System.Linq.Enumerable.First%2A>per restituire il primo elemento in un elenco.</xref:System.Linq.Enumerable.First%2A></span><span class="sxs-lookup"><span data-stu-id="1eab6-114">Use <xref:System.Linq.Enumerable.First%2A> to return the first element in a list.</span></span> <span data-ttu-id="1eab6-115">Utilizzare <xref:System.Linq.Enumerable.Take%2A>per restituire il primo numero n di elementi.</xref:System.Linq.Enumerable.Take%2A></span><span class="sxs-lookup"><span data-stu-id="1eab6-115">Use <xref:System.Linq.Enumerable.Take%2A> to return the first n number of elements.</span></span> <span data-ttu-id="1eab6-116">Specificare un ordinamento decrescente per inserire gli elementi più piccoli all'inizio dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="1eab6-116">Specify a descending sort order to put the smallest elements at the start of the list.</span></span>  
  
 <span data-ttu-id="1eab6-117">La query effettua a un metodo separato per ottenere le dimensioni del file in byte per gestire una possibile eccezione generata nel caso in cui è stato eliminato un file in un altro thread nel periodo di tempo dopo il <xref:System.IO.FileInfo>è stato creato l'oggetto nella chiamata a `GetFiles`.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="1eab6-117">The query calls out to a separate method to obtain the file size in bytes in order to consume the possible exception that will be raised in the case where a file was deleted on another thread in the time period since the <xref:System.IO.FileInfo> object was created in the call to `GetFiles`.</span></span> <span data-ttu-id="1eab6-118">Anche il <xref:System.IO.FileInfo>oggetto è già stato creato, l'eccezione può verificarsi perché un <xref:System.IO.FileInfo>oggetto tenta di aggiornare il relativo <xref:System.IO.FileInfo.Length%2A>proprietà utilizzando la dimensione più corrente in byte la prima volta che si accede alla proprietà.</xref:System.IO.FileInfo.Length%2A> </xref:System.IO.FileInfo> </xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="1eab6-118">Even through the <xref:System.IO.FileInfo> object has already been created, the exception can occur because a <xref:System.IO.FileInfo> object will try to refresh its <xref:System.IO.FileInfo.Length%2A> property by using the most current size in bytes the first time the property is accessed.</span></span> <span data-ttu-id="1eab6-119">Inserendo questa operazione in un blocco try-catch all'esterno della query, si seguita la regola di evitare operazioni di query che possono causare effetti collaterali.</span><span class="sxs-lookup"><span data-stu-id="1eab6-119">By putting this operation in a try-catch block outside the query, we follow the rule of avoiding operations in queries that can cause side-effects.</span></span> <span data-ttu-id="1eab6-120">In generale, è necessario prestare particolare attenzione durante l'utilizzo di eccezioni, per assicurarsi che un'applicazione non viene lasciata in uno stato sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="1eab6-120">In general, great care must be taken when consuming exceptions, to make sure that an application is not left in an unknown state.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1eab6-121">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="1eab6-121">Compiling the Code</span></span>  
 <span data-ttu-id="1eab6-122">Creare un progetto destinato a .NET Framework versione 3.5 o versione successiva con un riferimento a System.Core.dll e una `Imports` istruzione per lo spazio dei nomi System. Linq.</span><span class="sxs-lookup"><span data-stu-id="1eab6-122">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eab6-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1eab6-123">See Also</span></span>  
 <span data-ttu-id="1eab6-124">[LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) </span><span class="sxs-lookup"><span data-stu-id="1eab6-124">[LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) </span></span>  
<span data-ttu-id="1eab6-125"> [Directory di File (Visual Basic) e LINQ](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)</span><span class="sxs-lookup"><span data-stu-id="1eab6-125"> [LINQ and File Directories (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)</span></span>
