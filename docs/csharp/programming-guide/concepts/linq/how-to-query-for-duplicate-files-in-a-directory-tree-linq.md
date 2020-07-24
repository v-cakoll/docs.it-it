---
title: Come eseguire una query per i file duplicati in un albero di directory (LINQ) (C#)
description: Informazioni su come usare LINQ in C# per eseguire query per i nomi di file duplicati in directory diverse e su come eseguire una query per i file la cui dimensione e i tempi di ultima scrittura corrispondono.
ms.date: 07/20/2015
ms.assetid: 1ff5562b-0d30-46d1-b426-a04e8f78c840
ms.openlocfilehash: 72acb0e0823138821d321ed3845ff7ac137aee0c
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104564"
---
# <a name="how-to-query-for-duplicate-files-in-a-directory-tree-linq-c"></a><span data-ttu-id="c7858-103">Come eseguire una query per i file duplicati in un albero di directory (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="c7858-103">How to query for duplicate files in a directory tree (LINQ) (C#)</span></span>
<span data-ttu-id="c7858-104">Talvolta i file con lo stesso nome possono trovarsi in più di una cartella.</span><span class="sxs-lookup"><span data-stu-id="c7858-104">Sometimes files that have the same name may be located in more than one folder.</span></span> <span data-ttu-id="c7858-105">Ad esempio, nella cartella di installazione di Visual Studio diverse cartelle hanno un file readme.htm.</span><span class="sxs-lookup"><span data-stu-id="c7858-105">For example, under the Visual Studio installation folder, several folders have a readme.htm file.</span></span> <span data-ttu-id="c7858-106">In questo esempio viene illustrato come eseguire una query per trovare tali nomi di file duplicati in una cartella radice specificata.</span><span class="sxs-lookup"><span data-stu-id="c7858-106">This example shows how to query for such duplicate file names under a specified root folder.</span></span> <span data-ttu-id="c7858-107">Nel secondo esempio viene illustrato come eseguire una query per i file la cui dimensione e i tempi di ultima scrittura corrispondono.</span><span class="sxs-lookup"><span data-stu-id="c7858-107">The second example shows how to query for files whose size and LastWrite times also match.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7858-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="c7858-108">Example</span></span>  
  
```csharp  
class QueryDuplicateFileNames  
{  
    static void Main(string[] args)  
    {  
        // Uncomment QueryDuplicates2 to run that query.  
        QueryDuplicates();  
        // QueryDuplicates2();  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit.");  
        Console.ReadKey();  
    }  
  
    static void QueryDuplicates()  
    {  
        // Change the root drive or folder if necessary  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\";  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        // used in WriteLine to keep the lines shorter  
        int charsToSkip = startFolder.Length;  
  
        // var can be used for convenience with groups.  
        var queryDupNames =  
            from file in fileList  
            group file.FullName.Substring(charsToSkip) by file.Name into fileGroup  
            where fileGroup.Count() > 1  
            select fileGroup;  
  
        // Pass the query to a method that will  
        // output one page at a time.  
        PageOutput<string, string>(queryDupNames);  
    }  
  
    // A Group key that can be passed to a separate method.  
    // Override Equals and GetHashCode to define equality for the key.  
    // Override ToString to provide a friendly name for Key.ToString()  
    class PortableKey  
    {  
        public string Name { get; set; }  
        public DateTime LastWriteTime { get; set; }  
        public long Length { get; set; }  
  
        public override bool Equals(object obj)  
        {  
            PortableKey other = (PortableKey)obj;  
            return other.LastWriteTime == this.LastWriteTime &&  
                   other.Length == this.Length &&  
                   other.Name == this.Name;  
        }  
  
        public override int GetHashCode()  
        {  
            string str = $"{this.LastWriteTime}{this.Length}{this.Name}";
            return str.GetHashCode();  
        }  
        public override string ToString()  
        {  
            return $"{this.Name} {this.Length} {this.LastWriteTime}";
        }  
    }  
    static void QueryDuplicates2()  
    {  
        // Change the root drive or folder if necessary.  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\Common7";  
  
        // Make the lines shorter for the console display  
        int charsToSkip = startFolder.Length;  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        // Note the use of a compound key. Files that match  
        // all three properties belong to the same group.  
        // A named type is used to enable the query to be  
        // passed to another method. Anonymous types can also be used  
        // for composite keys but cannot be passed across method boundaries  
        //
        var queryDupFiles =  
            from file in fileList  
            group file.FullName.Substring(charsToSkip) by  
                new PortableKey { Name = file.Name, LastWriteTime = file.LastWriteTime, Length = file.Length } into fileGroup  
            where fileGroup.Count() > 1  
            select fileGroup;  
  
        var list = queryDupFiles.ToList();  
  
        int i = queryDupFiles.Count();  
  
        PageOutput<PortableKey, string>(queryDupFiles);  
    }  
  
    // A generic method to page the output of the QueryDuplications methods  
    // Here the type of the group must be specified explicitly. "var" cannot  
    // be used in method signatures. This method does not display more than one  
    // group per page.  
    private static void PageOutput<K, V>(IEnumerable<System.Linq.IGrouping<K, V>> groupByExtList)  
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
                Console.WriteLine("Filename = {0}", filegroup.Key.ToString() == String.Empty ? "[none]" : filegroup.Key.ToString());  
  
                // Get 'numLines' number of items starting at number 'currentLine'.  
                var resultPage = filegroup.Skip(currentLine).Take(numLines);  
  
                //Execute the resultPage query  
                foreach (var fileName in resultPage)  
                {  
                    Console.WriteLine("\t{0}", fileName);  
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
  
 <span data-ttu-id="c7858-109">La prima query usa una chiave semplice per determinare una corrispondenza. Individua i file che hanno lo stesso nome ma contenuto diverso.</span><span class="sxs-lookup"><span data-stu-id="c7858-109">The first query uses a simple key to determine a match; this finds files that have the same name but whose contents might be different.</span></span> <span data-ttu-id="c7858-110">La seconda query usa una chiave composta per individuare la corrispondenza con tre proprietà dell'oggetto <xref:System.IO.FileInfo>.</span><span class="sxs-lookup"><span data-stu-id="c7858-110">The second query uses a compound key to match against three properties of the <xref:System.IO.FileInfo> object.</span></span> <span data-ttu-id="c7858-111">Questa query individuerà file che hanno lo stesso nome e contenuto simile o identico.</span><span class="sxs-lookup"><span data-stu-id="c7858-111">This query is much more likely to find files that have the same name and similar or identical content.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c7858-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="c7858-112">Compiling the Code</span></span>  
 <span data-ttu-id="c7858-113">Creare un progetto di applicazione console C# con direttive `using` per gli spazi dei nomi System.Linq e System.IO.</span><span class="sxs-lookup"><span data-stu-id="c7858-113">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7858-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7858-114">See also</span></span>

- [<span data-ttu-id="c7858-115">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="c7858-115">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)
- [<span data-ttu-id="c7858-116">Directory di file e LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="c7858-116">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)
