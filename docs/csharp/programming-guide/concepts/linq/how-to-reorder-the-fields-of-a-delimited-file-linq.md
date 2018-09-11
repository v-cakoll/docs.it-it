---
title: 'Procedura: Riordinare i campi di un file delimitato (LINQ) (C#)'
ms.date: 07/20/2015
ms.assetid: 4e62d82c-61b7-4f18-b9a1-86723746d7d2
ms.openlocfilehash: 24d1bf9825e00d0764846a0ae83ae73cd0ea03e1
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44080566"
---
# <a name="how-to-reorder-the-fields-of-a-delimited-file-linq-c"></a><span data-ttu-id="c5209-102">Procedura: Riordinare i campi di un file delimitato (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="c5209-102">How to: Reorder the Fields of a Delimited File (LINQ) (C#)</span></span>
<span data-ttu-id="c5209-103">Un file con valori delimitati da virgole (CSV) è un file di testo che spesso viene usato per archiviare dati di un foglio di calcolo o altri dati tabulari rappresentati da righe e colonne.</span><span class="sxs-lookup"><span data-stu-id="c5209-103">A comma-separated value (CSV) file is a text file that is often used to store spreadsheet data or other tabular data that is represented by rows and columns.</span></span> <span data-ttu-id="c5209-104">Usando il metodo <xref:System.String.Split%2A> per separare i campi, è molto semplice eseguire una query e modificare i file CSV tramite LINQ.</span><span class="sxs-lookup"><span data-stu-id="c5209-104">By using the <xref:System.String.Split%2A> method to separate the fields, it is very easy to query and manipulate CSV files by using LINQ.</span></span> <span data-ttu-id="c5209-105">In effetti la stessa tecnica può essere usata per riordinare le parti di qualsiasi riga di testo strutturata, non solo i file CSV.</span><span class="sxs-lookup"><span data-stu-id="c5209-105">In fact, the same technique can be used to reorder the parts of any structured line of text; it is not limited to CSV files.</span></span>  
  
 <span data-ttu-id="c5209-106">Nell'esempio seguente vengono usate tre colonne per rappresentare "cognome", "nome" e "ID" di alcuni studenti.</span><span class="sxs-lookup"><span data-stu-id="c5209-106">In the following example, assume that the three columns represent students' "last name," "first name", and "ID."</span></span> <span data-ttu-id="c5209-107">I campi sono in ordine alfabetico in base ai cognomi degli studenti.</span><span class="sxs-lookup"><span data-stu-id="c5209-107">The fields are in alphabetical order based on the students' last names.</span></span> <span data-ttu-id="c5209-108">La query genera una nuova sequenza in cui la colonna ID viene visualizzata per prima, seguita da una seconda colonna che combina il nome e il cognome dello studente.</span><span class="sxs-lookup"><span data-stu-id="c5209-108">The query produces a new sequence in which the ID column appears first, followed by a second column that combines the student's first name and last name.</span></span> <span data-ttu-id="c5209-109">Le righe vengono riordinate in base al campo ID.</span><span class="sxs-lookup"><span data-stu-id="c5209-109">The lines are reordered according to the ID field.</span></span> <span data-ttu-id="c5209-110">I risultati vengono salvati in un nuovo file e i dati originali non vengono modificati.</span><span class="sxs-lookup"><span data-stu-id="c5209-110">The results are saved into a new file and the original data is not modified.</span></span>  
  
### <a name="to-create-the-data-file"></a><span data-ttu-id="c5209-111">Per creare il file di dati</span><span class="sxs-lookup"><span data-stu-id="c5209-111">To create the data file</span></span>  
  
1.  <span data-ttu-id="c5209-112">Copiare le righe seguenti in un file di testo normale denominato spreadsheet1.csv.</span><span class="sxs-lookup"><span data-stu-id="c5209-112">Copy the following lines into a plain text file that is named spreadsheet1.csv.</span></span> <span data-ttu-id="c5209-113">Salvare il file nella cartella del progetto.</span><span class="sxs-lookup"><span data-stu-id="c5209-113">Save the file in your project folder.</span></span>  
  
    ```  
    Adams,Terry,120  
    Fakhouri,Fadi,116  
    Feng,Hanying,117  
    Garcia,Cesar,114  
    Garcia,Debra,115  
    Garcia,Hugo,118  
    Mortensen,Sven,113  
    O'Donnell,Claire,112  
    Omelchenko,Svetlana,111  
    Tucker,Lance,119  
    Tucker,Michael,122  
    Zabokritski,Eugene,121  
    ```  
  
## <a name="example"></a><span data-ttu-id="c5209-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="c5209-114">Example</span></span>  
  
```csharp  
class CSVFiles  
{  
    static void Main(string[] args)  
    {  
        // Create the IEnumerable data source  
        string[] lines = System.IO.File.ReadAllLines(@"../../../spreadsheet1.csv");  
  
        // Create the query. Put field 2 first, then  
        // reverse and combine fields 0 and 1 from the old field  
        IEnumerable<string> query =  
            from line in lines  
            let x = line.Split(',')  
            orderby x[2]  
            select x[2] + ", " + (x[1] + " " + x[0]);  
  
        // Execute the query and write out the new file. Note that WriteAllLines  
        // takes a string[], so ToArray is called on the query.  
        System.IO.File.WriteAllLines(@"../../../spreadsheet2.csv", query.ToArray());  
  
        Console.WriteLine("Spreadsheet2.csv written to disk. Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output to spreadsheet2.csv:  
111, Svetlana Omelchenko  
112, Claire O'Donnell  
113, Sven Mortensen  
114, Cesar Garcia  
115, Debra Garcia  
116, Fadi Fakhouri  
117, Hanying Feng  
118, Hugo Garcia  
119, Lance Tucker  
120, Terry Adams  
121, Eugene Zabokritski  
122, Michael Tucker  
 */  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c5209-115">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="c5209-115">Compiling the Code</span></span>  
 <span data-ttu-id="c5209-116">Creare un progetto che usi .NET Framework versione 3.5 o successiva con un riferimento a System.Core.dll e alle direttive `using` per gli spazi dei nomi System.Linq e System.IO.</span><span class="sxs-lookup"><span data-stu-id="c5209-116">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5209-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5209-117">See Also</span></span>

- [<span data-ttu-id="c5209-118">LINQ e stringhe (C#)</span><span class="sxs-lookup"><span data-stu-id="c5209-118">LINQ and Strings (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)  
- [<span data-ttu-id="c5209-119">Directory di file e LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="c5209-119">LINQ and File Directories (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)  
- [<span data-ttu-id="c5209-120">Procedura: generare XML da file CSV (C#)</span><span class="sxs-lookup"><span data-stu-id="c5209-120">How to: Generate XML from CSV Files (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-generate-xml-from-csv-files.md)
