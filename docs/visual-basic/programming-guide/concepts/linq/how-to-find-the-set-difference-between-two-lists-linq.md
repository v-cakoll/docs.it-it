---
title: 'Procedura: Trovare la differenza dei set tra due elenchi (LINQ)'
ms.date: 07/20/2015
ms.assetid: b5b25474-10a8-4df6-aab5-75621bb6b68e
ms.openlocfilehash: f533b63b40325b34c5881c1e2f14aa4e576191c7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396597"
---
# <a name="how-to-find-the-set-difference-between-two-lists-linq-visual-basic"></a>Procedura: trovare la differenza dei set tra due elenchi (LINQ) (Visual Basic)
In questo esempio viene illustrato come usare LINQ per confrontare due elenchi di stringhe e restituire le righe presenti in names1.txt ma non in names2.txt.  
  
### <a name="to-create-the-data-files"></a>Per creare i file di dati  
  
1. Copiare names1. txt e names2. txt nella cartella della soluzione, come illustrato in [procedura: combinare e confrontare raccolte di stringhe (LINQ) (Visual Basic)](how-to-combine-and-compare-string-collections-linq.md).  
  
## <a name="example"></a>Esempio  
  
```vb  
Class CompareLists  
  
    Shared Sub Main()  
  
        ' Create the IEnumerable data sources.  
        Dim names1 As String() = System.IO.File.ReadAllLines("../../../names1.txt")  
        Dim names2 As String() = System.IO.File.ReadAllLines("../../../names2.txt")  
  
        ' Create the query. Note that method syntax must be used here.  
        Dim differenceQuery = names1.Except(names2)  
        Console.WriteLine("The following lines are in names1.txt but not names2.txt")  
  
        ' Execute the query.  
        For Each name As String In differenceQuery  
            Console.WriteLine(name)  
        Next  
  
        ' Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
End Class  
' Output:  
' The following lines are in names1.txt but not names2.txt  
' Potra, Cristina  
' Noriega, Fabricio  
' Aw, Kam Foo  
' Toyoshima, Tim  
' Guy, Wey Yuan  
' Garcia, Debra  
```  
  
 Alcuni tipi di operazioni di query in Visual Basic, ad esempio <xref:System.Linq.Enumerable.Except%2A> ,, <xref:System.Linq.Enumerable.Distinct%2A> <xref:System.Linq.Enumerable.Union%2A> e <xref:System.Linq.Enumerable.Concat%2A> , possono essere espressi solo nella sintassi basata su metodo.  
  
## <a name="compile-the-code"></a>Compilare il codice  
Creare un progetto di applicazione console Visual Basic con un' `Imports` istruzione per lo spazio dei nomi System. Linq.
  
## <a name="see-also"></a>Vedere anche

- [LINQ and Strings (Visual Basic)](linq-and-strings.md) (LINQ e le stringhe (Visual Basic))
