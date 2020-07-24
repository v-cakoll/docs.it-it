---
title: Come eseguire una query per il file o i file più grandi in un albero di directory (LINQ) (C#)
description: Questo esempio C# mostra cinque query LINQ correlate alle dimensioni del file in byte. È possibile modificarli per eseguire una query su altre proprietà dell'oggetto FileInfo.
ms.date: 07/20/2015
ms.assetid: 20c8a917-0552-4514-b489-0b8b6a4c3b4c
ms.openlocfilehash: c06c6017d6fd1efd6412729c5df63a2b819908a6
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104378"
---
# <a name="how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq-c"></a><span data-ttu-id="7b563-104">Come eseguire una query per il file o i file più grandi in un albero di directory (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="7b563-104">How to query for the largest file or files in a directory tree (LINQ) (C#)</span></span>
<span data-ttu-id="7b563-105">Questo esempio illustra cinque query relative alla dimensione dei file in byte:</span><span class="sxs-lookup"><span data-stu-id="7b563-105">This example shows five queries related to file size in bytes:</span></span>  
  
- <span data-ttu-id="7b563-106">Come recuperare la dimensione in byte del file più grande.</span><span class="sxs-lookup"><span data-stu-id="7b563-106">How to retrieve the size in bytes of the largest file.</span></span>  
  
- <span data-ttu-id="7b563-107">Come recuperare la dimensione in byte del file più piccolo.</span><span class="sxs-lookup"><span data-stu-id="7b563-107">How to retrieve the size in bytes of the smallest file.</span></span>  
  
- <span data-ttu-id="7b563-108">Come recuperare il file più grande o più piccolo dell'oggetto <xref:System.IO.FileInfo> da una o più cartelle in una cartella radice specificata.</span><span class="sxs-lookup"><span data-stu-id="7b563-108">How to retrieve the <xref:System.IO.FileInfo> object largest or smallest file from one or more folders under a specified root folder.</span></span>  
  
- <span data-ttu-id="7b563-109">Come recuperare una sequenza, ad esempio i 10 file più grandi.</span><span class="sxs-lookup"><span data-stu-id="7b563-109">How to retrieve a sequence such as the 10 largest files.</span></span>  
  
- <span data-ttu-id="7b563-110">Come ordinare i file in gruppi in base alla dimensione del file in byte, ignorando i file di dimensione inferiore a un valore specificato.</span><span class="sxs-lookup"><span data-stu-id="7b563-110">How to order files into groups based on their file size in bytes, ignoring files that are less than a specified size.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b563-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="7b563-111">Example</span></span>  
 <span data-ttu-id="7b563-112">L'esempio seguente contiene cinque query distinte che illustrano come eseguire una query e raggruppare i file in base alle dimensioni in byte.</span><span class="sxs-lookup"><span data-stu-id="7b563-112">The following example contains five separate queries that show how to query and group files, depending on their file size in bytes.</span></span> <span data-ttu-id="7b563-113">È possibile modificare facilmente questi esempi per basare la query su un'altra proprietà dell'oggetto <xref:System.IO.FileInfo>.</span><span class="sxs-lookup"><span data-stu-id="7b563-113">You can easily modify these examples to base the query on some other property of the <xref:System.IO.FileInfo> object.</span></span>  
  
```csharp  
class QueryBySize  
{  
    static void Main(string[] args)  
    {  
        QueryFilesBySize();  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
  
    private static void QueryFilesBySize()  
    {  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\";  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        //Return the size of the largest file  
        long maxSize =  
            (from file in fileList  
             let len = GetFileLength(file)  
             select len)  
             .Max();  
  
        Console.WriteLine("The length of the largest file under {0} is {1}",  
            startFolder, maxSize);  
  
        // Return the FileInfo object for the largest file  
        // by sorting and selecting from beginning of list  
        System.IO.FileInfo longestFile =  
            (from file in fileList  
             let len = GetFileLength(file)  
             where len > 0  
             orderby len descending  
             select file)  
            .First();  
  
        Console.WriteLine("The largest file under {0} is {1} with a length of {2} bytes",  
                            startFolder, longestFile.FullName, longestFile.Length);  
  
        //Return the FileInfo of the smallest file  
        System.IO.FileInfo smallestFile =  
            (from file in fileList  
             let len = GetFileLength(file)  
             where len > 0  
             orderby len ascending  
             select file).First();  
  
        Console.WriteLine("The smallest file under {0} is {1} with a length of {2} bytes",  
                            startFolder, smallestFile.FullName, smallestFile.Length);  
  
        //Return the FileInfos for the 10 largest files  
        // queryTenLargest is an IEnumerable<System.IO.FileInfo>  
        var queryTenLargest =  
            (from file in fileList  
             let len = GetFileLength(file)  
             orderby len descending  
             select file).Take(10);  
  
        Console.WriteLine("The 10 largest files under {0} are:", startFolder);  
  
        foreach (var v in queryTenLargest)  
        {  
            Console.WriteLine("{0}: {1} bytes", v.FullName, v.Length);  
        }  
  
        // Group the files according to their size, leaving out  
        // files that are less than 200000 bytes.
        var querySizeGroups =  
            from file in fileList  
            let len = GetFileLength(file)  
            where len > 0  
            group file by (len / 100000) into fileGroup  
            where fileGroup.Key >= 2  
            orderby fileGroup.Key descending  
            select fileGroup;  
  
        foreach (var filegroup in querySizeGroups)  
        {  
            Console.WriteLine(filegroup.Key.ToString() + "00000");  
            foreach (var item in filegroup)  
            {  
                Console.WriteLine("\t{0}: {1}", item.Name, item.Length);  
            }  
        }  
    }  
  
    // This method is used to swallow the possible exception  
    // that can be raised when accessing the FileInfo.Length property.  
    // In this particular case, it is safe to swallow the exception.  
    static long GetFileLength(System.IO.FileInfo fi)  
    {  
        long retval;  
        try  
        {  
            retval = fi.Length;  
        }  
        catch (System.IO.FileNotFoundException)  
        {  
            // If a file is no longer present,  
            // just add zero bytes to the total.  
            retval = 0;  
        }  
        return retval;  
    }  
  
}  
```  
  
 <span data-ttu-id="7b563-114">Per restituire uno o più oggetti <xref:System.IO.FileInfo> completi, è necessario che la query esamini prima di tutto ogni oggetto nell'origine dati e quindi ordini gli oggetti in base al valore della relativa proprietà Length.</span><span class="sxs-lookup"><span data-stu-id="7b563-114">To return one or more complete <xref:System.IO.FileInfo> objects, the query first must examine each one in the data source, and then sort them by the value of their Length property.</span></span> <span data-ttu-id="7b563-115">La query potrà quindi restituire il singolo oggetto o la sequenza con le lunghezze maggiori.</span><span class="sxs-lookup"><span data-stu-id="7b563-115">Then it can return the single one or the sequence with the greatest lengths.</span></span> <span data-ttu-id="7b563-116">Usare <xref:System.Linq.Enumerable.First%2A> per restituire il primo elemento di un elenco.</span><span class="sxs-lookup"><span data-stu-id="7b563-116">Use <xref:System.Linq.Enumerable.First%2A> to return the first element in a list.</span></span> <span data-ttu-id="7b563-117">Usare <xref:System.Linq.Enumerable.Take%2A> per restituire i primi n elementi.</span><span class="sxs-lookup"><span data-stu-id="7b563-117">Use <xref:System.Linq.Enumerable.Take%2A> to return the first n number of elements.</span></span> <span data-ttu-id="7b563-118">Specificare un ordinamento decrescente per inserire gli elementi più piccoli all'inizio dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="7b563-118">Specify a descending sort order to put the smallest elements at the start of the list.</span></span>  
  
 <span data-ttu-id="7b563-119">La query effettua una chiamata a un metodo separato per ottenere le dimensioni dei file in byte per gestire la possibile eccezione che viene generata nel caso in cui un file sia stato eliminato in un altro thread nel periodo trascorso dalla creazione dell'oggetto <xref:System.IO.FileInfo> nella chiamata a `GetFiles`.</span><span class="sxs-lookup"><span data-stu-id="7b563-119">The query calls out to a separate method to obtain the file size in bytes in order to consume the possible exception that will be raised in the case where a file was deleted on another thread in the time period since the <xref:System.IO.FileInfo> object was created in the call to `GetFiles`.</span></span> <span data-ttu-id="7b563-120">Anche se l'oggetto <xref:System.IO.FileInfo> è già stato creato, è possibile che si verifichi un'eccezione perché un oggetto <xref:System.IO.FileInfo> tenterà di aggiornare la relativa proprietà <xref:System.IO.FileInfo.Length%2A> usando le dimensioni in byte più recenti quando viene eseguito per la prima volta l'accesso alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="7b563-120">Even through the <xref:System.IO.FileInfo> object has already been created, the exception can occur because a <xref:System.IO.FileInfo> object will try to refresh its <xref:System.IO.FileInfo.Length%2A> property by using the most current size in bytes the first time the property is accessed.</span></span> <span data-ttu-id="7b563-121">Inserendo questa operazione in un blocco try/catch all'esterno della query, si segue la regola di evitare le operazioni nelle query che possono causare effetti collaterali.</span><span class="sxs-lookup"><span data-stu-id="7b563-121">By putting this operation in a try-catch block outside the query, we follow the rule of avoiding operations in queries that can cause side-effects.</span></span> <span data-ttu-id="7b563-122">In generale, è necessario prestare particolare attenzione durante la gestione delle eccezioni per assicurarsi che un'applicazione non venga lasciata in uno stato sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="7b563-122">In general, great care must be taken when consuming exceptions, to make sure that an application is not left in an unknown state.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7b563-123">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="7b563-123">Compiling the Code</span></span>  
<span data-ttu-id="7b563-124">Creare un progetto di applicazione console C# con direttive `using` per gli spazi dei nomi System.Linq e System.IO.</span><span class="sxs-lookup"><span data-stu-id="7b563-124">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b563-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b563-125">See also</span></span>

- [<span data-ttu-id="7b563-126">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="7b563-126">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)
- [<span data-ttu-id="7b563-127">Directory di file e LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="7b563-127">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)
