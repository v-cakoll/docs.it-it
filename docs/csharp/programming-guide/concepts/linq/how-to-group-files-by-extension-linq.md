---
title: Come raggruppare i file in base all'estensione (LINQ) (C
ms.date: 07/20/2015
ms.assetid: 21a98320-a5a1-4981-82d8-6a637e7d9018
ms.openlocfilehash: 2ee1fa1291f5845c818395dfe038ec5894adc863
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79169155"
---
# <a name="how-to-group-files-by-extension-linq-c"></a><span data-ttu-id="4dea4-102">Come raggruppare i file in base all'estensione (LINQ) (C</span><span class="sxs-lookup"><span data-stu-id="4dea4-102">How to group files by extension (LINQ) (C#)</span></span>
<span data-ttu-id="4dea4-103">Questo esempio illustra come usare LINQ per eseguire operazioni avanzate di raggruppamento e ordinamento su elenchi di file o cartelle.</span><span class="sxs-lookup"><span data-stu-id="4dea4-103">This example shows how LINQ can be used to perform advanced grouping and sorting operations on lists of files or folders.</span></span> <span data-ttu-id="4dea4-104">Illustra anche come disporre l'output nella finestra della console usando i metodi <xref:System.Linq.Enumerable.Skip%2A> e <xref:System.Linq.Enumerable.Take%2A>.</span><span class="sxs-lookup"><span data-stu-id="4dea4-104">It also shows how to page output in the console window by using the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4dea4-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="4dea4-105">Example</span></span>  
 <span data-ttu-id="4dea4-106">La query seguente illustra come raggruppare il contenuto di un albero di directory specificato per l'estensione dei nomi dei file.</span><span class="sxs-lookup"><span data-stu-id="4dea4-106">The following query shows how to group the contents of a specified directory tree by the file name extension.</span></span>  
  
```csharp  
class GroupByExtension  
{  
    // This query will sort all the files under the specified folder  
    //  and subfolder into groups keyed by the file extension.  
    private static void Main()  
    {  
        // Take a snapshot of the file system.  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\Common7";  
  
        // Used in WriteLine to trim output lines.  
        int trimLength = startFolder.Length;  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        // Create the query.  
        var queryGroupByExt =  
            from file in fileList  
            group file by file.Extension.ToLower() into fileGroup  
            orderby fileGroup.Key  
            select fileGroup;  
  
        // Display one group at a time. If the number of
        // entries is greater than the number of lines  
        // in the console window, then page the output.  
        PageOutput(trimLength, queryGroupByExt);  
    }  
  
    // This method specifically handles group queries of FileInfo objects with string keys.  
    // It can be modified to work for any long listings of data. Note that explicit typing  
    // must be used in method signatures. The groupbyExtList parameter is a query that produces  
    // groups of FileInfo objects with string keys.  
    private static void PageOutput(int rootLength,  
                                    IEnumerable<System.Linq.IGrouping<string, System.IO.FileInfo>> groupByExtList)  
    {  
        // Flag to break out of paging loop.  
        bool goAgain = true;  
  
        // "3" = 1 line for extension + 1 for "Press any key" + 1 for input cursor.  
        int numLines = Console.WindowHeight - 3;  
  
        // Iterate through the outer collection of groups.  
        foreach (var filegroup in groupByExtList)  
        {  
            // Start a new extension at the top of a page.  
            int currentLine = 0;  
  
            // Output only as many lines of the current group as will fit in the window.  
            do  
            {  
                Console.Clear();  
                Console.WriteLine(filegroup.Key == String.Empty ? "[none]" : filegroup.Key);  
  
                // Get 'numLines' number of items starting at number 'currentLine'.  
                var resultPage = filegroup.Skip(currentLine).Take(numLines);  
  
                //Execute the resultPage query  
                foreach (var f in resultPage)  
                {  
                    Console.WriteLine("\t{0}", f.FullName.Substring(rootLength));  
                }  
  
                // Increment the line counter.  
                currentLine += numLines;  
  
                // Give the user a chance to escape.  
                Console.WriteLine("Press any key to continue or the 'End' key to break...");  
                ConsoleKey key = Console.ReadKey().Key;  
                if (key == ConsoleKey.End)  
                {  
                    goAgain = false;  
                    break;  
                }  
            } while (currentLine < filegroup.Count());  
  
            if (goAgain == false)  
                break;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="4dea4-107">L'output di questo programma può essere lungo, a seconda dei dettagli del file system locale e dell'impostazione di `startFolder`.</span><span class="sxs-lookup"><span data-stu-id="4dea4-107">The output from this program can be long, depending on the details of the local file system and what the `startFolder` is set to.</span></span> <span data-ttu-id="4dea4-108">Per abilitare la visualizzazione di tutti i risultati, in questo esempio viene illustrato come scorrere i risultati.</span><span class="sxs-lookup"><span data-stu-id="4dea4-108">To enable viewing of all results, this example shows how to page through results.</span></span> <span data-ttu-id="4dea4-109">È possibile applicare le stesse tecniche ad applicazioni Windows e Web.</span><span class="sxs-lookup"><span data-stu-id="4dea4-109">The same techniques can be applied to Windows and Web applications.</span></span> <span data-ttu-id="4dea4-110">Si noti che, poiché il codice dispone gli elementi in un gruppo, è necessario un ciclo `foreach` annidato.</span><span class="sxs-lookup"><span data-stu-id="4dea4-110">Notice that because the code pages the items in a group, a nested `foreach` loop is required.</span></span> <span data-ttu-id="4dea4-111">È disponibile anche una logica aggiuntiva per calcolare la posizione corrente nell'elenco e per consentire all'utente di interrompere lo scorrimento e uscire dal programma.</span><span class="sxs-lookup"><span data-stu-id="4dea4-111">There is also some additional logic to compute the current position in the list, and to enable the user to stop paging and exit the program.</span></span> <span data-ttu-id="4dea4-112">In questo caso particolare la query di scorrimento viene eseguita sui risultati memorizzati nella cache della query originale.</span><span class="sxs-lookup"><span data-stu-id="4dea4-112">In this particular case, the paging query is run against the cached results from the original query.</span></span> <span data-ttu-id="4dea4-113">In altri contesti, come ad esempio LINQ to SQL, la memorizzazione nella cache non è necessaria.</span><span class="sxs-lookup"><span data-stu-id="4dea4-113">In other contexts, such as LINQ to SQL, such caching is not required.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4dea4-114">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="4dea4-114">Compiling the Code</span></span>  
 <span data-ttu-id="4dea4-115">Creare un progetto di applicazione console C# con direttive `using` per gli spazi dei nomi System.Linq e System.IO.</span><span class="sxs-lookup"><span data-stu-id="4dea4-115">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dea4-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4dea4-116">See also</span></span>

- [<span data-ttu-id="4dea4-117">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="4dea4-117">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)
- [<span data-ttu-id="4dea4-118">Directory di file e LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="4dea4-118">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)
