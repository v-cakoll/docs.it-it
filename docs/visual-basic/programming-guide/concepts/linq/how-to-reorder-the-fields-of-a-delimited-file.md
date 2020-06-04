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
# <a name="how-to-reorder-the-fields-of-a-delimited-file-linq-visual-basic"></a>Procedura: riordinare i campi di un file delimitato (LINQ) (Visual Basic)

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

## <a name="see-also"></a>Vedere anche

- [LINQ and Strings (Visual Basic)](linq-and-strings.md) (LINQ e le stringhe (Visual Basic))
- [LINQ and File Directories (Visual Basic)](linq-and-file-directories.md) (LINQ e directory file (Visual Basic))
- [Procedura: generare XML da file CSV](how-to-generate-xml-from-csv-files.md)
