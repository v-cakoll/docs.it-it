---
title: 'Procedura: Eseguire una query per trovare il numero totale di byte in un set di cartelle (LINQ) (C#)'
ms.date: 07/20/2015
ms.assetid: a01bd1d4-133c-4ca2-aa4e-e93e81d6076c
ms.openlocfilehash: 7a11e30a41ce171d516d3ea00a0e8664efe33520
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2018
ms.locfileid: "44185928"
---
# <a name="how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq-c"></a><span data-ttu-id="bf9e9-102">Procedura: Eseguire una query per trovare il numero totale di byte in un set di cartelle (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="bf9e9-102">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (C#)</span></span>
<span data-ttu-id="bf9e9-103">Questo esempio illustra come recuperare il numero totale di byte usati da tutti i file in una cartella specificata e in tutte le relative sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="bf9e9-103">This example shows how to retrieve the total number of bytes used by all the files in a specified folder and all its subfolders.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf9e9-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="bf9e9-104">Example</span></span>  
 <span data-ttu-id="bf9e9-105">Il metodo <xref:System.Linq.Enumerable.Sum%2A> aggiunge i valori di tutti gli elementi selezionati nella clausola `select`.</span><span class="sxs-lookup"><span data-stu-id="bf9e9-105">The <xref:System.Linq.Enumerable.Sum%2A> method adds the values of all the items selected in the `select` clause.</span></span> <span data-ttu-id="bf9e9-106">È possibile modificare facilmente questa query per recuperare il file più grande o più piccolo nell'albero di directory specificato chiamando il metodo <xref:System.Linq.Enumerable.Min%2A> o <xref:System.Linq.Enumerable.Max%2A> invece di <xref:System.Linq.Enumerable.Sum%2A>.</span><span class="sxs-lookup"><span data-stu-id="bf9e9-106">You can easily modify this query to retrieve the biggest or smallest file in the specified directory tree by calling the <xref:System.Linq.Enumerable.Min%2A> or <xref:System.Linq.Enumerable.Max%2A> method instead of <xref:System.Linq.Enumerable.Sum%2A>.</span></span>  
  
```csharp  
class QuerySize  
{  
    public static void Main()  
    {  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\VC#";  
  
        // Take a snapshot of the file system.  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<string> fileList = System.IO.Directory.GetFiles(startFolder, "*.*", System.IO.SearchOption.AllDirectories);  
  
        var fileQuery = from file in fileList  
                        select GetFileLength(file);  
  
        // Cache the results to avoid multiple trips to the file system.  
        long[] fileLengths = fileQuery.ToArray();  
  
        // Return the size of the largest file  
        long largestFile = fileLengths.Max();  
  
        // Return the total number of bytes in all the files under the specified folder.  
        long totalBytes = fileLengths.Sum();  
  
        Console.WriteLine("There are {0} bytes in {1} files under {2}",  
            totalBytes, fileList.Count(), startFolder);  
        Console.WriteLine("The largest files is {0} bytes.", largestFile);  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit.");  
        Console.ReadKey();  
    }  
  
    // This method is used to swallow the possible exception  
    // that can be raised when accessing the System.IO.FileInfo.Length property.  
    static long GetFileLength(string filename)  
    {  
        long retval;  
        try  
        {  
            System.IO.FileInfo fi = new System.IO.FileInfo(filename);  
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
  
 <span data-ttu-id="bf9e9-107">Se è necessario contare solo il numero di byte in un albero di directory specificato, è possibile eseguire questa operazione in modo più efficiente senza creare una query LINQ che comporta un sovraccarico dovuto alla creazione della raccolta di elenchi come origine dati.</span><span class="sxs-lookup"><span data-stu-id="bf9e9-107">If you only have to count the number of bytes in a specified directory tree, you can do this more efficiently without creating a LINQ query, which incurs the overhead of creating the list collection as a data source.</span></span> <span data-ttu-id="bf9e9-108">I vantaggi dell'uso di LINQ aumentano per le query più complesse oppure quando è necessario eseguire più query nella stessa origine dati.</span><span class="sxs-lookup"><span data-stu-id="bf9e9-108">The usefulness of the LINQ approach increases as the query becomes more complex, or when you have to run multiple queries against the same data source.</span></span>  
  
 <span data-ttu-id="bf9e9-109">La query effettua una chiamata a un metodo separato per ottenere la lunghezza del file.</span><span class="sxs-lookup"><span data-stu-id="bf9e9-109">The query calls out to a separate method to obtain the file length.</span></span> <span data-ttu-id="bf9e9-110">Questa operazione viene eseguita per gestire la possibile eccezione che viene generata nel caso in cui il file sia stato eliminato in un altro thread dopo la creazione dell'oggetto <xref:System.IO.FileInfo> nella chiamata a `GetFiles`.</span><span class="sxs-lookup"><span data-stu-id="bf9e9-110">It does this in order to consume the possible exception that will be raised if the file was deleted on another thread after the <xref:System.IO.FileInfo> object was created in the call to `GetFiles`.</span></span> <span data-ttu-id="bf9e9-111">Anche se l'oggetto <xref:System.IO.FileInfo> è già stato creato, è possibile che si verifichi un'eccezione perché un oggetto <xref:System.IO.FileInfo> tenterà di aggiornare la relativa proprietà <xref:System.IO.FileInfo.Length%2A> usando la lunghezza più recente quando viene eseguito per la prima volta l'accesso alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="bf9e9-111">Even though the <xref:System.IO.FileInfo> object has already been created, the exception can occur because a <xref:System.IO.FileInfo> object will try to refresh its <xref:System.IO.FileInfo.Length%2A> property with the most current length the first time the property is accessed.</span></span> <span data-ttu-id="bf9e9-112">Inserendo questa operazione in un blocco try/catch all'esterno della query, si evita di eseguire operazioni nelle query che possono causare effetti collaterali.</span><span class="sxs-lookup"><span data-stu-id="bf9e9-112">By putting this operation in a try-catch block outside the query, the code follows the rule of avoiding operations in queries that can cause side-effects.</span></span> <span data-ttu-id="bf9e9-113">In generale, è necessario prestare particolare attenzione durante la gestione delle eccezioni per assicurarsi che un'applicazione non venga lasciata in uno stato sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="bf9e9-113">In general, great care must be taken when you consume exceptions to make sure that an application is not left in an unknown state.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bf9e9-114">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="bf9e9-114">Compiling the Code</span></span>  
 <span data-ttu-id="bf9e9-115">Creare un progetto che usi .NET Framework 3.5 o versione successiva con un riferimento a System.Core.dll e alle direttive `using` per gli spazi dei nomi System.Linq e System.IO.</span><span class="sxs-lookup"><span data-stu-id="bf9e9-115">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to   System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf9e9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf9e9-116">See Also</span></span>

- [<span data-ttu-id="bf9e9-117">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="bf9e9-117">LINQ to Objects (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)  
- [<span data-ttu-id="bf9e9-118">Directory di file e LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="bf9e9-118">LINQ and File Directories (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)
