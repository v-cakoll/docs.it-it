---
title: 'Procedura: Eseguire una query per trovare i file con un attributo o un nome specifico (C#)'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 560e3879-b0b3-4549-ad02-0a53aff2f83c
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2bfb7e19dcb6562dfc9b9efd24bec93774dfbee9
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-query-for-files-with-a-specified-attribute-or-name-c"></a><span data-ttu-id="fcf11-102">Procedura: Eseguire una query per trovare i file con un attributo o un nome specifico (C#)</span><span class="sxs-lookup"><span data-stu-id="fcf11-102">How to: Query for Files with a Specified Attribute or Name (C#)</span></span>
<span data-ttu-id="fcf11-103">In questo esempio viene illustrato come trovare tutti i file con un'estensione del nome specificata, come ad esempio "txt", in un albero di directory specificato.</span><span class="sxs-lookup"><span data-stu-id="fcf11-103">This example shows how to find all files that have a specified file name extension (for example ".txt") in a specified directory tree.</span></span> <span data-ttu-id="fcf11-104">Viene anche illustrato come restituire il file più recente o meno recente nell'albero in base all'ora di creazione.</span><span class="sxs-lookup"><span data-stu-id="fcf11-104">It also shows how to return either the newest or oldest file in the tree based on the creation time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcf11-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="fcf11-105">Example</span></span>  
  
```csharp  
class FindFileByExtension  
{  
    // This query will produce the full path for all .txt files  
    // under the specified folder including subfolders.  
    // It orders the list according to the file name.  
    static void Main()  
    {  
        string startFolder = @"c:\program files\Microsoft Visual Studio 9.0\";  
  
        // Take a snapshot of the file system.  
        System.IO.DirectoryInfo dir = new System.IO.DirectoryInfo(startFolder);  
  
        // This method assumes that the application has discovery permissions  
        // for all folders under the specified path.  
        IEnumerable<System.IO.FileInfo> fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
        //Create the query  
        IEnumerable<System.IO.FileInfo> fileQuery =  
            from file in fileList  
            where file.Extension == ".txt"  
            orderby file.Name  
            select file;  
  
        //Execute the query. This might write out a lot of files!  
        foreach (System.IO.FileInfo fi in fileQuery)  
        {  
            Console.WriteLine(fi.FullName);  
        }  
  
        // Create and execute a new query by using the previous   
        // query as a starting point. fileQuery is not   
        // executed again until the call to Last()  
        var newestFile =  
            (from file in fileQuery  
             orderby file.CreationTime  
             select new { file.FullName, file.CreationTime })  
            .Last();  
  
        Console.WriteLine("\r\nThe newest .txt file is {0}. Creation time: {1}",  
            newestFile.FullName, newestFile.CreationTime);  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fcf11-106">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="fcf11-106">Compiling the Code</span></span>  
 <span data-ttu-id="fcf11-107">Creare un progetto che usi .NET Framework 3.5 o versione successiva con un riferimento a System.Core.dll e alle direttive `using` per gli spazi dei nomi System.Linq e System.IO.</span><span class="sxs-lookup"><span data-stu-id="fcf11-107">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to   System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcf11-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcf11-108">See Also</span></span>  
 <span data-ttu-id="fcf11-109">[LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md) </span><span class="sxs-lookup"><span data-stu-id="fcf11-109">[LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md) </span></span>  
 [<span data-ttu-id="fcf11-110">Directory di file e LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="fcf11-110">LINQ and File Directories (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)

