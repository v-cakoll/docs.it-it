---
title: 'Procedura: Riordinare i campi di un file delimitato (LINQ)'
ms.date: 07/20/2015
ms.assetid: c451c7db-663b-4daf-b8ba-a2093095d672
ms.openlocfilehash: 6f87374978425e0d51542c6eceda23697d7a3a67
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397895"
---
# <a name="how-to-reorder-the-fields-of-a-delimited-file-linq-visual-basic"></a><span data-ttu-id="389ae-102">Procedura: riordinare i campi di un file delimitato (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="389ae-102">How to: Reorder the Fields of a Delimited File (LINQ) (Visual Basic)</span></span>

<span data-ttu-id="389ae-103">Un file con valori delimitati da virgole (CSV) è un file di testo che spesso viene usato per archiviare dati di un foglio di calcolo o altri dati tabulari rappresentati da righe e colonne.</span><span class="sxs-lookup"><span data-stu-id="389ae-103">A comma-separated value (CSV) file is a text file that is often used to store spreadsheet data or other tabular data that is represented by rows and columns.</span></span> <span data-ttu-id="389ae-104">Usando il metodo <xref:System.String.Split%2A> per separare i campi, è molto semplice eseguire una query e modificare i file CSV tramite LINQ.</span><span class="sxs-lookup"><span data-stu-id="389ae-104">By using the <xref:System.String.Split%2A> method to separate the fields, it is very easy to query and manipulate CSV files by using LINQ.</span></span> <span data-ttu-id="389ae-105">In effetti la stessa tecnica può essere usata per riordinare le parti di qualsiasi riga di testo strutturata, non solo i file CSV.</span><span class="sxs-lookup"><span data-stu-id="389ae-105">In fact, the same technique can be used to reorder the parts of any structured line of text; it is not limited to CSV files.</span></span>

<span data-ttu-id="389ae-106">Nell'esempio seguente vengono usate tre colonne per rappresentare "cognome", "nome" e "ID" di alcuni studenti.</span><span class="sxs-lookup"><span data-stu-id="389ae-106">In the following example, assume that the three columns represent students' "last name," "first name", and "ID."</span></span> <span data-ttu-id="389ae-107">I campi sono in ordine alfabetico in base ai cognomi degli studenti.</span><span class="sxs-lookup"><span data-stu-id="389ae-107">The fields are in alphabetical order based on the students' last names.</span></span> <span data-ttu-id="389ae-108">La query genera una nuova sequenza in cui la colonna ID viene visualizzata per prima, seguita da una seconda colonna che combina il nome e il cognome dello studente.</span><span class="sxs-lookup"><span data-stu-id="389ae-108">The query produces a new sequence in which the ID column appears first, followed by a second column that combines the student's first name and last name.</span></span> <span data-ttu-id="389ae-109">Le righe vengono riordinate in base al campo ID.</span><span class="sxs-lookup"><span data-stu-id="389ae-109">The lines are reordered according to the ID field.</span></span> <span data-ttu-id="389ae-110">I risultati vengono salvati in un nuovo file e i dati originali non vengono modificati.</span><span class="sxs-lookup"><span data-stu-id="389ae-110">The results are saved into a new file and the original data is not modified.</span></span>

### <a name="to-create-the-data-file"></a><span data-ttu-id="389ae-111">Per creare il file di dati</span><span class="sxs-lookup"><span data-stu-id="389ae-111">To create the data file</span></span>

1. <span data-ttu-id="389ae-112">Copiare le righe seguenti in un file di testo normale denominato spreadsheet1.csv.</span><span class="sxs-lookup"><span data-stu-id="389ae-112">Copy the following lines into a plain text file that is named spreadsheet1.csv.</span></span> <span data-ttu-id="389ae-113">Salvare il file nella cartella del progetto.</span><span class="sxs-lookup"><span data-stu-id="389ae-113">Save the file in your project folder.</span></span>

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

## <a name="example"></a><span data-ttu-id="389ae-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="389ae-114">Example</span></span>

```vb
Class CSVFiles

    Shared Sub Main()

        ' Create the IEnumerable data source.
        Dim lines As String() = System.IO.File.ReadAllLines("../../../spreadsheet1.csv")

        ' Execute the query. Put field 2 first, then
        ' reverse and combine fields 0 and 1 from the old field
        Dim lineQuery = From line In lines
                        Let x = line.Split(New Char() {","})
                        Order By x(2)
                        Select x(2) & ", " & (x(1) & " " & x(0))

        ' Execute the query and write out the new file. Note that WriteAllLines
        ' takes a string array, so ToArray is called on the query.
        System.IO.File.WriteAllLines("../../../spreadsheet2.csv", lineQuery.ToArray())

        ' Keep console window open in debug mode.
        Console.WriteLine("Spreadsheet2.csv written to disk. Press any key to exit")
        Console.ReadKey()
    End Sub
End Class
' Output to spreadsheet2.csv:
' 111, Svetlana Omelchenko
' 112, Claire O'Donnell
' 113, Sven Mortensen
' 114, Cesar Garcia
' 115, Debra Garcia
' 116, Fadi Fakhouri
' 117, Hanying Feng
' 118, Hugo Garcia
' 119, Lance Tucker
' 120, Terry Adams
' 121, Eugene Zabokritski
' 122, Michael Tucker
```

## <a name="see-also"></a><span data-ttu-id="389ae-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="389ae-115">See also</span></span>

- <span data-ttu-id="389ae-116">[LINQ and Strings (Visual Basic)](linq-and-strings.md) (LINQ e le stringhe (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="389ae-116">[LINQ and Strings (Visual Basic)](linq-and-strings.md)</span></span>
- <span data-ttu-id="389ae-117">[LINQ and File Directories (Visual Basic)](linq-and-file-directories.md) (LINQ e directory file (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="389ae-117">[LINQ and File Directories (Visual Basic)](linq-and-file-directories.md)</span></span>
- [<span data-ttu-id="389ae-118">Procedura: generare XML da file CSV</span><span class="sxs-lookup"><span data-stu-id="389ae-118">How to: Generate XML from CSV Files</span></span>](how-to-generate-xml-from-csv-files.md)
