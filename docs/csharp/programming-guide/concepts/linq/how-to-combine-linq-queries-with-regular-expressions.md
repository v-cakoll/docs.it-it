---
title: Come combinare query LINQ con espressioni regolari (C#)
description: Questo esempio crea un'espressione regolare per la corrispondenza nelle stringhe di testo usando la classe Regex in C#.
ms.date: 07/20/2015
ms.assetid: 6b003b65-20a4-4ca2-929e-2ee3f215aecc
ms.openlocfilehash: af63d096e3c2f19ed557180d82d606989a016120
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105346"
---
# <a name="how-to-combine-linq-queries-with-regular-expressions-c"></a>Come combinare query LINQ con espressioni regolari (C#)
In questo esempio viene illustrato come usare la classe <xref:System.Text.RegularExpressions.Regex> per creare un'espressione regolare per una corrispondenza più complessa nelle stringhe di testo. La query LINQ consente di filtrare esattamente i file che si vuole cercare tramite l'espressione regolare e di dare forma ai risultati.  
  
## <a name="example"></a>Esempio  
  
```csharp  
class QueryWithRegEx  
{  
    public static void Main()  
    {  
        // Modify this path as necessary so that it accesses your version of Visual Studio.  
        string startFolder = @"C:\Program Files (x86)\Microsoft Visual Studio 14.0\";  
        // One of the following paths may be more appropriate on your computer.  
        //string startFolder = @"C:\Program Files (x86)\Microsoft Visual Studio\2017\";  
  
        // Take a snapshot of the file system.  
        IEnumerable<System.IO.FileInfo> fileList = GetFiles(startFolder);  
  
        // Create the regular expression to find all things "Visual".  
        System.Text.RegularExpressions.Regex searchTerm =  
            new System.Text.RegularExpressions.Regex(@"Visual (Basic|C#|C\+\+|Studio)");  
  
        // Search the contents of each .htm file.  
        // Remove the where clause to find even more matchedValues!  
        // This query produces a list of files where a match  
        // was found, and a list of the matchedValues in that file.  
        // Note: Explicit typing of "Match" in select clause.  
        // This is required because MatchCollection is not a
        // generic IEnumerable collection.  
        var queryMatchingFiles =  
            from file in fileList  
            where file.Extension == ".htm"  
            let fileText = System.IO.File.ReadAllText(file.FullName)  
            let matches = searchTerm.Matches(fileText)  
            where matches.Count > 0  
            select new  
            {  
                name = file.FullName,  
                matchedValues = from System.Text.RegularExpressions.Match match in matches  
                                select match.Value  
            };  
  
        // Execute the query.  
        Console.WriteLine("The term \"{0}\" was found in:", searchTerm.ToString());  
  
        foreach (var v in queryMatchingFiles)  
        {  
            // Trim the path a bit, then write
            // the file name in which a match was found.  
            string s = v.name.Substring(startFolder.Length - 1);  
            Console.WriteLine(s);  
  
            // For this file, write out all the matching strings  
            foreach (var v2 in v.matchedValues)  
            {  
                Console.WriteLine("  " + v2);  
            }  
        }  
  
        // Keep the console window open in debug mode  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
  
    // This method assumes that the application has discovery
    // permissions for all folders under the specified path.  
    static IEnumerable<System.IO.FileInfo> GetFiles(string path)  
    {  
        if (!System.IO.Directory.Exists(path))  
            throw new System.IO.DirectoryNotFoundException();  
  
        string[] fileNames = null;  
        List<System.IO.FileInfo> files = new List<System.IO.FileInfo>();  
  
        fileNames = System.IO.Directory.GetFiles(path, "*.*", System.IO.SearchOption.AllDirectories);  
        foreach (string name in fileNames)  
        {  
            files.Add(new System.IO.FileInfo(name));  
        }  
        return files;  
    }  
}  
```  
  
 Si noti che è anche possibile eseguire una query sull'oggetto <xref:System.Text.RegularExpressions.MatchCollection> restituito da una ricerca `RegEx`. In questo esempio viene generato nei risultati solo il valore di ogni corrispondenza. Tuttavia, è anche possibile usare LINQ per eseguire tutti i tipi di filtro, ordinamento e raggruppamento sulla raccolta. Poiché <xref:System.Text.RegularExpressions.MatchCollection> è una raccolta non generica <xref:System.Collections.IEnumerable>, è necessario dichiarare esplicitamente il tipo della variabile di intervallo nella query.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Creare un progetto di applicazione console C# con direttive `using` per gli spazi dei nomi System.Linq e System.IO.  
  
## <a name="see-also"></a>Vedere anche

- [LINQ e stringhe (C#)](./linq-and-strings.md)
- [Directory di file e LINQ (C#)](./linq-and-file-directories.md)
