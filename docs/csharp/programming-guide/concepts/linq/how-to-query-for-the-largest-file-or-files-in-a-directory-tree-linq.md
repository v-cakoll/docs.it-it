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
# <a name="how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq-c"></a>Come eseguire una query per il file o i file più grandi in un albero di directory (LINQ) (C#)
Questo esempio illustra cinque query relative alla dimensione dei file in byte:  
  
- Come recuperare la dimensione in byte del file più grande.  
  
- Come recuperare la dimensione in byte del file più piccolo.  
  
- Come recuperare il file più grande o più piccolo dell'oggetto <xref:System.IO.FileInfo> da una o più cartelle in una cartella radice specificata.  
  
- Come recuperare una sequenza, ad esempio i 10 file più grandi.  
  
- Come ordinare i file in gruppi in base alla dimensione del file in byte, ignorando i file di dimensione inferiore a un valore specificato.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente contiene cinque query distinte che illustrano come eseguire una query e raggruppare i file in base alle dimensioni in byte. È possibile modificare facilmente questi esempi per basare la query su un'altra proprietà dell'oggetto <xref:System.IO.FileInfo>.  
  
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
  
 Per restituire uno o più oggetti <xref:System.IO.FileInfo> completi, è necessario che la query esamini prima di tutto ogni oggetto nell'origine dati e quindi ordini gli oggetti in base al valore della relativa proprietà Length. La query potrà quindi restituire il singolo oggetto o la sequenza con le lunghezze maggiori. Usare <xref:System.Linq.Enumerable.First%2A> per restituire il primo elemento di un elenco. Usare <xref:System.Linq.Enumerable.Take%2A> per restituire i primi n elementi. Specificare un ordinamento decrescente per inserire gli elementi più piccoli all'inizio dell'elenco.  
  
 La query effettua una chiamata a un metodo separato per ottenere le dimensioni dei file in byte per gestire la possibile eccezione che viene generata nel caso in cui un file sia stato eliminato in un altro thread nel periodo trascorso dalla creazione dell'oggetto <xref:System.IO.FileInfo> nella chiamata a `GetFiles`. Anche se l'oggetto <xref:System.IO.FileInfo> è già stato creato, è possibile che si verifichi un'eccezione perché un oggetto <xref:System.IO.FileInfo> tenterà di aggiornare la relativa proprietà <xref:System.IO.FileInfo.Length%2A> usando le dimensioni in byte più recenti quando viene eseguito per la prima volta l'accesso alla proprietà. Inserendo questa operazione in un blocco try/catch all'esterno della query, si segue la regola di evitare le operazioni nelle query che possono causare effetti collaterali. In generale, è necessario prestare particolare attenzione durante la gestione delle eccezioni per assicurarsi che un'applicazione non venga lasciata in uno stato sconosciuto.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
Creare un progetto di applicazione console C# con direttive `using` per gli spazi dei nomi System.Linq e System.IO.

## <a name="see-also"></a>Vedere anche

- [LINQ to Objects (C#)](./linq-to-objects.md)
- [Directory di file e LINQ (C#)](./linq-and-file-directories.md)
