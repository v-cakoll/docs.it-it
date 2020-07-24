---
title: Come eseguire una query sul contenuto dei file di testo in una cartella (LINQ) (C#)
description: Informazioni su come usare LINQ in C# per eseguire query su tutti i file in un albero di directory, aprire ogni file ed esaminarne il contenuto.
ms.date: 07/20/2015
ms.assetid: f5b4dce7-1a34-4eb4-9bf1-60d5bdda264c
ms.openlocfilehash: 216edc2ee6fc43fd06a3c89b1b6b73f693f752f8
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104261"
---
# <a name="how-to-query-the-contents-of-text-files-in-a-folder-linq-c"></a><span data-ttu-id="d7a35-103">Come eseguire una query sul contenuto dei file di testo in una cartella (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="d7a35-103">How to query the contents of text files in a folder (LINQ) (C#)</span></span>
<span data-ttu-id="d7a35-104">Questo esempio illustra come eseguire una query su tutti i file in un albero di directory specificato, aprire ogni file e controllarne il contenuto.</span><span class="sxs-lookup"><span data-stu-id="d7a35-104">This example shows how to query over all the files in a specified directory tree, open each file, and inspect its contents.</span></span> <span data-ttu-id="d7a35-105">Questo tipo di tecnica può essere usato per creare indici o indici inversi del contenuto di un albero di directory.</span><span class="sxs-lookup"><span data-stu-id="d7a35-105">This type of technique could be used to create indexes or reverse indexes of the contents of a directory tree.</span></span> <span data-ttu-id="d7a35-106">In questo esempio viene eseguita una semplice ricerca di una stringa.</span><span class="sxs-lookup"><span data-stu-id="d7a35-106">A simple string search is performed in this example.</span></span> <span data-ttu-id="d7a35-107">Tuttavia, con un'espressione regolare è possibile eseguire tipi di criteri di ricerca più complessi.</span><span class="sxs-lookup"><span data-stu-id="d7a35-107">However, more complex types of pattern matching can be performed with a regular expression.</span></span> <span data-ttu-id="d7a35-108">Per ulteriori informazioni, vedere [come combinare query LINQ con espressioni regolari (C#)](./how-to-combine-linq-queries-with-regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="d7a35-108">For more information, see [How to combine LINQ queries with regular expressions (C#)](./how-to-combine-linq-queries-with-regular-expressions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7a35-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="d7a35-109">Example</span></span>  
  
```csharp  
class QueryContents  
{  
    public static void Main()  
    {  
        // Modify this path as necessary.  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\";  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        string searchTerm = @"Visual Studio";  
  
        // Search the contents of each file.  
        // A regular expression created with the RegEx class  
        // could be used instead of the Contains method.  
        // queryMatchingFiles is an IEnumerable<string>.  
        var queryMatchingFiles =  
            from file in fileList  
            where file.Extension == ".htm"  
            let fileText = GetFileText(file.FullName)  
            where fileText.Contains(searchTerm)  
            select file.FullName;  
  
        // Execute the query.  
        Console.WriteLine("The term \"{0}\" was found in:", searchTerm);  
        foreach (string filename in queryMatchingFiles)  
        {  
            Console.WriteLine(filename);  
        }  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
  
    // Read the contents of the file.  
    static string GetFileText(string name)  
    {  
        string fileContents = String.Empty;  
  
        // If the file has been deleted since we took
        // the snapshot, ignore it and return the empty string.  
        if (System.IO.File.Exists(name))  
        {  
            fileContents = System.IO.File.ReadAllText(name);  
        }  
        return fileContents;  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d7a35-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="d7a35-110">Compiling the Code</span></span>  
<span data-ttu-id="d7a35-111">Creare un progetto di applicazione console C# con direttive `using` per gli spazi dei nomi System.Linq e System.IO.</span><span class="sxs-lookup"><span data-stu-id="d7a35-111">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d7a35-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7a35-112">See also</span></span>

- [<span data-ttu-id="d7a35-113">Directory di file e LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="d7a35-113">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)
- [<span data-ttu-id="d7a35-114">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="d7a35-114">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)
