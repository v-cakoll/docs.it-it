---
title: Come confrontare il contenuto di due cartelle (LINQ) (C#)
description: Questo esempio illustra tre modi per confrontare gli elenchi di file usando le query LINQ in C#. Adattare queste tecniche per confrontare sequenze di oggetti di qualsiasi tipo.
ms.date: 07/20/2015
ms.assetid: c7c4870e-c500-4de3-afa4-2c8e07f510e6
ms.openlocfilehash: 3cdac57d3d746aa2290c51d1263a7d42dc3463e0
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105328"
---
# <a name="how-to-compare-the-contents-of-two-folders-linq-c"></a><span data-ttu-id="2344e-104">Come confrontare il contenuto di due cartelle (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="2344e-104">How to compare the contents of two folders (LINQ) (C#)</span></span>
<span data-ttu-id="2344e-105">In questo esempio vengono illustrati tre modi per confrontare due elenchi di file:</span><span class="sxs-lookup"><span data-stu-id="2344e-105">This example demonstrates three ways to compare two file listings:</span></span>  
  
- <span data-ttu-id="2344e-106">Eseguendo una query su un valore booleano che specifica se i due elenchi di file sono identici.</span><span class="sxs-lookup"><span data-stu-id="2344e-106">By querying for a Boolean value that specifies whether the two file lists are identical.</span></span>  
  
- <span data-ttu-id="2344e-107">Eseguendo una query sull'intersezione per recuperare i file presenti in entrambe le cartelle.</span><span class="sxs-lookup"><span data-stu-id="2344e-107">By querying for the intersection to retrieve the files that are in both folders.</span></span>  
  
- <span data-ttu-id="2344e-108">Eseguendo una query sulla differenza tra set per recuperare i file che sono presenti in una cartella, ma non nell'altra.</span><span class="sxs-lookup"><span data-stu-id="2344e-108">By querying for the set difference to retrieve the files that are in one folder but not the other.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="2344e-109">Le tecniche illustrate di seguito possono essere adattate per confrontare le sequenze di oggetti di qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="2344e-109">The techniques shown here can be adapted to compare sequences of objects of any type.</span></span>  
  
 <span data-ttu-id="2344e-110">La classe `FileComparer` descritta in questo argomento illustra come usare una classe di operatori di confronto personalizzata insieme con gli operatori query standard.</span><span class="sxs-lookup"><span data-stu-id="2344e-110">The `FileComparer` class shown here demonstrates how to use a custom comparer class together with the Standard Query Operators.</span></span> <span data-ttu-id="2344e-111">La classe non è destinata all'uso in scenari reali.</span><span class="sxs-lookup"><span data-stu-id="2344e-111">The class is not intended for use in real-world scenarios.</span></span> <span data-ttu-id="2344e-112">Si limita a usare il nome e la lunghezza in byte di ogni file per determinare se il contenuto di ogni cartella è identico o meno.</span><span class="sxs-lookup"><span data-stu-id="2344e-112">It just uses the name and length in bytes of each file to determine whether the contents of each folder are identical or not.</span></span> <span data-ttu-id="2344e-113">In uno scenario reale è necessario modificare questo operatore di confronto per eseguire un controllo di uguaglianza più rigoroso.</span><span class="sxs-lookup"><span data-stu-id="2344e-113">In a real-world scenario, you should modify this comparer to perform a more rigorous equality check.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2344e-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="2344e-114">Example</span></span>  
  
```csharp  
namespace QueryCompareTwoDirs  
{  
    class CompareDirs  
    {  
  
        static void Main(string[] args)  
        {  
  
            // Create two identical or different temporary folders
            // on a local drive and change these file paths.  
            string pathA = @"C:\TestDir";  
            string pathB = @"C:\TestDir2";  
  
            System.IO.DirectoryInfo dir1 = new System.IO.DirectoryInfo(pathA);  
            System.IO.DirectoryInfo dir2 = new System.IO.DirectoryInfo(pathB);  
  
            // Take a snapshot of the file system.  
            IEnumerable<System.IO.FileInfo> list1 = dir1.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
            IEnumerable<System.IO.FileInfo> list2 = dir2.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
            //A custom file comparer defined below  
            FileCompare myFileCompare = new FileCompare();  
  
            // This query determines whether the two folders contain  
            // identical file lists, based on the custom file comparer  
            // that is defined in the FileCompare class.  
            // The query executes immediately because it returns a bool.  
            bool areIdentical = list1.SequenceEqual(list2, myFileCompare);  
  
            if (areIdentical == true)  
            {  
                Console.WriteLine("the two folders are the same");  
            }  
            else  
            {  
                Console.WriteLine("The two folders are not the same");  
            }  
  
            // Find the common files. It produces a sequence and doesn't
            // execute until the foreach statement.  
            var queryCommonFiles = list1.Intersect(list2, myFileCompare);  
  
            if (queryCommonFiles.Any())  
            {  
                Console.WriteLine("The following files are in both folders:");  
                foreach (var v in queryCommonFiles)  
                {  
                    Console.WriteLine(v.FullName); //shows which items end up in result list  
                }  
            }  
            else  
            {  
                Console.WriteLine("There are no common files in the two folders.");  
            }  
  
            // Find the set difference between the two folders.  
            // For this example we only check one way.  
            var queryList1Only = (from file in list1  
                                  select file).Except(list2, myFileCompare);  
  
            Console.WriteLine("The following files are in list1 but not list2:");  
            foreach (var v in queryList1Only)  
            {  
                Console.WriteLine(v.FullName);  
            }  
  
            // Keep the console window open in debug mode.  
            Console.WriteLine("Press any key to exit.");  
            Console.ReadKey();  
        }  
    }  
  
    // This implementation defines a very simple comparison  
    // between two FileInfo objects. It only compares the name  
    // of the files being compared and their length in bytes.  
    class FileCompare : System.Collections.Generic.IEqualityComparer<System.IO.FileInfo>  
    {  
        public FileCompare() { }  
  
        public bool Equals(System.IO.FileInfo f1, System.IO.FileInfo f2)  
        {  
            return (f1.Name == f2.Name &&  
                    f1.Length == f2.Length);  
        }  
  
        // Return a hash that reflects the comparison criteria. According to the
        // rules for IEqualityComparer<T>, if Equals is true, then the hash codes must  
        // also be equal. Because equality as defined here is a simple value equality, not  
        // reference identity, it is possible that two or more objects will produce the same  
        // hash code.  
        public int GetHashCode(System.IO.FileInfo fi)  
        {  
            string s = $"{fi.Name}{fi.Length}";
            return s.GetHashCode();  
        }  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2344e-115">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="2344e-115">Compiling the Code</span></span>  
 <span data-ttu-id="2344e-116">Creare un progetto di applicazione console C# con direttive `using` per gli spazi dei nomi System.Linq e System.IO.</span><span class="sxs-lookup"><span data-stu-id="2344e-116">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2344e-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2344e-117">See also</span></span>

- [<span data-ttu-id="2344e-118">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="2344e-118">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)
- [<span data-ttu-id="2344e-119">Directory di file e LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="2344e-119">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)
