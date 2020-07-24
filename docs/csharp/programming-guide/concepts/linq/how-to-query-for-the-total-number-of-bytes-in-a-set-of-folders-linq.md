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
# <a name="how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq-c"></a>Come eseguire una query per il numero totale di byte in un set di cartelle (LINQ) (C#)
Questo esempio illustra come recuperare il numero totale di byte usati da tutti i file in una cartella specificata e in tutte le relative sottocartelle.  
  
## <a name="example"></a>Esempio  
 Il metodo <xref:System.Linq.Enumerable.Sum%2A> aggiunge i valori di tutti gli elementi selezionati nella clausola `select`. È possibile modificare facilmente questa query per recuperare il file più grande o più piccolo nell'albero di directory specificato chiamando il metodo <xref:System.Linq.Enumerable.Min%2A> o <xref:System.Linq.Enumerable.Max%2A> invece di <xref:System.Linq.Enumerable.Sum%2A>.  
  
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
  
 Se è necessario contare solo il numero di byte in un albero di directory specificato, è possibile eseguire questa operazione in modo più efficiente senza creare una query LINQ che comporta un sovraccarico dovuto alla creazione della raccolta di elenchi come origine dati. I vantaggi dell'uso di LINQ aumentano per le query più complesse oppure quando è necessario eseguire più query nella stessa origine dati.  
  
 La query effettua una chiamata a un metodo separato per ottenere la lunghezza del file. Questa operazione viene eseguita per gestire la possibile eccezione che viene generata nel caso in cui il file sia stato eliminato in un altro thread dopo la creazione dell'oggetto <xref:System.IO.FileInfo> nella chiamata a `GetFiles`. Anche se l'oggetto <xref:System.IO.FileInfo> è già stato creato, è possibile che si verifichi un'eccezione perché un oggetto <xref:System.IO.FileInfo> tenterà di aggiornare la relativa proprietà <xref:System.IO.FileInfo.Length%2A> usando la lunghezza più recente quando viene eseguito per la prima volta l'accesso alla proprietà. Inserendo questa operazione in un blocco try/catch all'esterno della query, si evita di eseguire operazioni nelle query che possono causare effetti collaterali. In generale, è necessario prestare particolare attenzione durante la gestione delle eccezioni per assicurarsi che un'applicazione non venga lasciata in uno stato sconosciuto.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
Creare un progetto di applicazione console C# con direttive `using` per gli spazi dei nomi System.Linq e System.IO.
  
## <a name="see-also"></a>Vedere anche

- [LINQ to Objects (C#)](./linq-to-objects.md)
- [Directory di file e LINQ (C#)](./linq-and-file-directories.md)
