---
title: Come eseguire una query per il numero totale di byte in un set di cartelle (LINQ) (C#)
description: Informazioni su come usare LINQ in C# per trovare il numero totale di byte usati da tutti i file in una cartella specificata e nelle relative sottocartelle.
ms.date: 07/20/2015
ms.assetid: a01bd1d4-133c-4ca2-aa4e-e93e81d6076c
ms.openlocfilehash: 964d92a55599d60388f7add937c7f7338f697817
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104298"
---
# <a name="how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq-c"></a><span data-ttu-id="3bcf2-103">Come eseguire una query per il numero totale di byte in un set di cartelle (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="3bcf2-103">How to query for the total number of bytes in a set of folders (LINQ) (C#)</span></span>
<span data-ttu-id="3bcf2-104">Questo esempio illustra come recuperare il numero totale di byte usati da tutti i file in una cartella specificata e in tutte le relative sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="3bcf2-104">This example shows how to retrieve the total number of bytes used by all the files in a specified folder and all its subfolders.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3bcf2-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="3bcf2-105">Example</span></span>  
 <span data-ttu-id="3bcf2-106">Il metodo <xref:System.Linq.Enumerable.Sum%2A> aggiunge i valori di tutti gli elementi selezionati nella clausola `select`.</span><span class="sxs-lookup"><span data-stu-id="3bcf2-106">The <xref:System.Linq.Enumerable.Sum%2A> method adds the values of all the items selected in the `select` clause.</span></span> <span data-ttu-id="3bcf2-107">È possibile modificare facilmente questa query per recuperare il file più grande o più piccolo nell'albero di directory specificato chiamando il metodo <xref:System.Linq.Enumerable.Min%2A> o <xref:System.Linq.Enumerable.Max%2A> invece di <xref:System.Linq.Enumerable.Sum%2A>.</span><span class="sxs-lookup"><span data-stu-id="3bcf2-107">You can easily modify this query to retrieve the biggest or smallest file in the specified directory tree by calling the <xref:System.Linq.Enumerable.Min%2A> or <xref:System.Linq.Enumerable.Max%2A> method instead of <xref:System.Linq.Enumerable.Sum%2A>.</span></span>  
  
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
  
 <span data-ttu-id="3bcf2-108">Se è necessario contare solo il numero di byte in un albero di directory specificato, è possibile eseguire questa operazione in modo più efficiente senza creare una query LINQ che comporta un sovraccarico dovuto alla creazione della raccolta di elenchi come origine dati.</span><span class="sxs-lookup"><span data-stu-id="3bcf2-108">If you only have to count the number of bytes in a specified directory tree, you can do this more efficiently without creating a LINQ query, which incurs the overhead of creating the list collection as a data source.</span></span> <span data-ttu-id="3bcf2-109">I vantaggi dell'uso di LINQ aumentano per le query più complesse oppure quando è necessario eseguire più query nella stessa origine dati.</span><span class="sxs-lookup"><span data-stu-id="3bcf2-109">The usefulness of the LINQ approach increases as the query becomes more complex, or when you have to run multiple queries against the same data source.</span></span>  
  
 <span data-ttu-id="3bcf2-110">La query effettua una chiamata a un metodo separato per ottenere la lunghezza del file.</span><span class="sxs-lookup"><span data-stu-id="3bcf2-110">The query calls out to a separate method to obtain the file length.</span></span> <span data-ttu-id="3bcf2-111">Questa operazione viene eseguita per gestire la possibile eccezione che viene generata nel caso in cui il file sia stato eliminato in un altro thread dopo la creazione dell'oggetto <xref:System.IO.FileInfo> nella chiamata a `GetFiles`.</span><span class="sxs-lookup"><span data-stu-id="3bcf2-111">It does this in order to consume the possible exception that will be raised if the file was deleted on another thread after the <xref:System.IO.FileInfo> object was created in the call to `GetFiles`.</span></span> <span data-ttu-id="3bcf2-112">Anche se l'oggetto <xref:System.IO.FileInfo> è già stato creato, è possibile che si verifichi un'eccezione perché un oggetto <xref:System.IO.FileInfo> tenterà di aggiornare la relativa proprietà <xref:System.IO.FileInfo.Length%2A> usando la lunghezza più recente quando viene eseguito per la prima volta l'accesso alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="3bcf2-112">Even though the <xref:System.IO.FileInfo> object has already been created, the exception can occur because a <xref:System.IO.FileInfo> object will try to refresh its <xref:System.IO.FileInfo.Length%2A> property with the most current length the first time the property is accessed.</span></span> <span data-ttu-id="3bcf2-113">Inserendo questa operazione in un blocco try/catch all'esterno della query, si evita di eseguire operazioni nelle query che possono causare effetti collaterali.</span><span class="sxs-lookup"><span data-stu-id="3bcf2-113">By putting this operation in a try-catch block outside the query, the code follows the rule of avoiding operations in queries that can cause side-effects.</span></span> <span data-ttu-id="3bcf2-114">In generale, è necessario prestare particolare attenzione durante la gestione delle eccezioni per assicurarsi che un'applicazione non venga lasciata in uno stato sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="3bcf2-114">In general, great care must be taken when you consume exceptions to make sure that an application is not left in an unknown state.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3bcf2-115">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="3bcf2-115">Compiling the Code</span></span>  
<span data-ttu-id="3bcf2-116">Creare un progetto di applicazione console C# con direttive `using` per gli spazi dei nomi System.Linq e System.IO.</span><span class="sxs-lookup"><span data-stu-id="3bcf2-116">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3bcf2-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3bcf2-117">See also</span></span>

- [<span data-ttu-id="3bcf2-118">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="3bcf2-118">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)
- [<span data-ttu-id="3bcf2-119">Directory di file e LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="3bcf2-119">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)
