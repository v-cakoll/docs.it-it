---
title: 'Procedura: eseguire una query per trovare il file o i file più grandi in un albero di directory (LINQ)'
ms.date: 07/20/2015
ms.assetid: 8c1c9f0c-95dd-4222-9be2-9ec026a13e81
ms.openlocfilehash: 34f2cd97cafbe142c9462e8d0cf7c17f9f0d16f9
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346063"
---
# <a name="how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq-visual-basic"></a><span data-ttu-id="91900-102">Procedura: eseguire una query per trovare il file o i file più grandi in un albero di directory (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="91900-102">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="91900-103">Questo esempio illustra cinque query relative alla dimensione dei file in byte:</span><span class="sxs-lookup"><span data-stu-id="91900-103">This example shows five queries related to file size in bytes:</span></span>  
  
- <span data-ttu-id="91900-104">Come recuperare la dimensione in byte del file più grande.</span><span class="sxs-lookup"><span data-stu-id="91900-104">How to retrieve the size in bytes of the largest file.</span></span>  
  
- <span data-ttu-id="91900-105">Come recuperare la dimensione in byte del file più piccolo.</span><span class="sxs-lookup"><span data-stu-id="91900-105">How to retrieve the size in bytes of the smallest file.</span></span>  
  
- <span data-ttu-id="91900-106">Come recuperare il file più grande o più piccolo dell'oggetto <xref:System.IO.FileInfo> da una o più cartelle in una cartella radice specificata.</span><span class="sxs-lookup"><span data-stu-id="91900-106">How to retrieve the <xref:System.IO.FileInfo> object largest or smallest file from one or more folders under a specified root folder.</span></span>  
  
- <span data-ttu-id="91900-107">Come recuperare una sequenza, ad esempio i 10 file più grandi.</span><span class="sxs-lookup"><span data-stu-id="91900-107">How to retrieve a sequence such as the 10 largest files.</span></span>  
  
- <span data-ttu-id="91900-108">Come ordinare i file in gruppi in base alla dimensione del file in byte, ignorando i file di dimensione inferiore a un valore specificato.</span><span class="sxs-lookup"><span data-stu-id="91900-108">How to order files into groups based on their file size in bytes, ignoring files that are less than a specified size.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91900-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="91900-109">Example</span></span>  
 <span data-ttu-id="91900-110">L'esempio seguente contiene cinque query distinte che illustrano come eseguire una query e raggruppare i file in base alle dimensioni in byte.</span><span class="sxs-lookup"><span data-stu-id="91900-110">The following example contains five separate queries that show how to query and group files, depending on their file size in bytes.</span></span> <span data-ttu-id="91900-111">È possibile modificare facilmente questi esempi per basare la query su un'altra proprietà dell'oggetto <xref:System.IO.FileInfo>.</span><span class="sxs-lookup"><span data-stu-id="91900-111">You can easily modify these examples to base the query on some other property of the <xref:System.IO.FileInfo> object.</span></span>  
  
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
  
 <span data-ttu-id="91900-112">Per restituire uno o più oggetti <xref:System.IO.FileInfo> completi, è necessario che la query esamini prima di tutto ogni oggetto nell'origine dati e quindi ordini gli oggetti in base al valore della relativa proprietà Length.</span><span class="sxs-lookup"><span data-stu-id="91900-112">To return one or more complete <xref:System.IO.FileInfo> objects, the query first must examine each one in the data source, and then sort them by the value of their Length property.</span></span> <span data-ttu-id="91900-113">La query potrà quindi restituire il singolo oggetto o la sequenza con le lunghezze maggiori.</span><span class="sxs-lookup"><span data-stu-id="91900-113">Then it can return the single one or the sequence with the greatest lengths.</span></span> <span data-ttu-id="91900-114">Usare <xref:System.Linq.Enumerable.First%2A> per restituire il primo elemento di un elenco.</span><span class="sxs-lookup"><span data-stu-id="91900-114">Use <xref:System.Linq.Enumerable.First%2A> to return the first element in a list.</span></span> <span data-ttu-id="91900-115">Usare <xref:System.Linq.Enumerable.Take%2A> per restituire i primi n elementi.</span><span class="sxs-lookup"><span data-stu-id="91900-115">Use <xref:System.Linq.Enumerable.Take%2A> to return the first n number of elements.</span></span> <span data-ttu-id="91900-116">Specificare un ordinamento decrescente per inserire gli elementi più piccoli all'inizio dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="91900-116">Specify a descending sort order to put the smallest elements at the start of the list.</span></span>  
  
 <span data-ttu-id="91900-117">La query effettua una chiamata a un metodo separato per ottenere le dimensioni dei file in byte per gestire la possibile eccezione che viene generata nel caso in cui un file sia stato eliminato in un altro thread nel periodo trascorso dalla creazione dell'oggetto <xref:System.IO.FileInfo> nella chiamata a `GetFiles`.</span><span class="sxs-lookup"><span data-stu-id="91900-117">The query calls out to a separate method to obtain the file size in bytes in order to consume the possible exception that will be raised in the case where a file was deleted on another thread in the time period since the <xref:System.IO.FileInfo> object was created in the call to `GetFiles`.</span></span> <span data-ttu-id="91900-118">Anche se l'oggetto <xref:System.IO.FileInfo> è già stato creato, è possibile che si verifichi un'eccezione perché un oggetto <xref:System.IO.FileInfo> tenterà di aggiornare la relativa proprietà <xref:System.IO.FileInfo.Length%2A> usando le dimensioni in byte più recenti quando viene eseguito per la prima volta l'accesso alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="91900-118">Even through the <xref:System.IO.FileInfo> object has already been created, the exception can occur because a <xref:System.IO.FileInfo> object will try to refresh its <xref:System.IO.FileInfo.Length%2A> property by using the most current size in bytes the first time the property is accessed.</span></span> <span data-ttu-id="91900-119">Inserendo questa operazione in un blocco try/catch all'esterno della query, si segue la regola di evitare le operazioni nelle query che possono causare effetti collaterali.</span><span class="sxs-lookup"><span data-stu-id="91900-119">By putting this operation in a try-catch block outside the query, we follow the rule of avoiding operations in queries that can cause side-effects.</span></span> <span data-ttu-id="91900-120">In generale, è necessario prestare particolare attenzione durante la gestione delle eccezioni per assicurarsi che un'applicazione non venga lasciata in uno stato sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="91900-120">In general, great care must be taken when consuming exceptions, to make sure that an application is not left in an unknown state.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="91900-121">Compilare il codice</span><span class="sxs-lookup"><span data-stu-id="91900-121">Compile the code</span></span>  
<span data-ttu-id="91900-122">Creare un progetto di applicazione console Visual Basic con un'istruzione `Imports` per lo spazio dei nomi System. Linq.</span><span class="sxs-lookup"><span data-stu-id="91900-122">Create a Visual Basic console application project, with an `Imports` statement for the System.Linq namespace.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="91900-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91900-123">See also</span></span>

- [<span data-ttu-id="91900-124">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="91900-124">LINQ to Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
- <span data-ttu-id="91900-125">[LINQ and File Directories (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md) (LINQ e directory file (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="91900-125">[LINQ and File Directories (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)</span></span>
