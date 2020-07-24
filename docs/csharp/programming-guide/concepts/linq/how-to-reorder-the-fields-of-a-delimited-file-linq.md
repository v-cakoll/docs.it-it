---
title: Come riordinare i campi di un file delimitato (LINQ) (C#)
description: Informazioni su come ridisporre i campi in un file con estensione CSV in LINQ in C#. Nell'esempio vengono modificati gli ordini di colonne, vengono uniti in colonne e le righe vengono ordinate in base a un valore di colonna.
ms.date: 07/20/2015
ms.assetid: 4e62d82c-61b7-4f18-b9a1-86723746d7d2
ms.openlocfilehash: 3ebc56b418d2732a296896a19d770136a56e2fbb
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103412"
---
# <a name="how-to-reorder-the-fields-of-a-delimited-file-linq-c"></a>Come riordinare i campi di un file delimitato (LINQ) (C#)
Un file con valori delimitati da virgole (CSV) è un file di testo che spesso viene usato per archiviare dati di un foglio di calcolo o altri dati tabulari rappresentati da righe e colonne. Usando il metodo <xref:System.String.Split%2A> per separare i campi, è molto semplice eseguire una query e modificare i file CSV tramite LINQ. In effetti la stessa tecnica può essere usata per riordinare le parti di qualsiasi riga di testo strutturata, non solo i file CSV.  
  
 Nell'esempio seguente vengono usate tre colonne per rappresentare "cognome", "nome" e "ID" di alcuni studenti. I campi sono in ordine alfabetico in base ai cognomi degli studenti. La query genera una nuova sequenza in cui la colonna ID viene visualizzata per prima, seguita da una seconda colonna che combina il nome e il cognome dello studente. Le righe vengono riordinate in base al campo ID. I risultati vengono salvati in un nuovo file e i dati originali non vengono modificati.  
  
### <a name="to-create-the-data-file"></a>Per creare il file di dati  
  
1. Copiare le righe seguenti in un file di testo normale denominato spreadsheet1.csv. Salvare il file nella cartella del progetto.  
  
    ```csv  
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
  
## <a name="example"></a>Esempio  
  
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
  
## <a name="compiling-the-code"></a>Compilazione del codice  
Creare un progetto di applicazione console C# con direttive `using` per gli spazi dei nomi System.Linq e System.IO.
  
## <a name="see-also"></a>Vedere anche

- [LINQ e stringhe (C#)](./linq-and-strings.md)
- [Directory di file e LINQ (C#)](./linq-and-file-directories.md)
- [Come generare XML da file CSV (C#)](./how-to-generate-xml-from-csv-files.md)
