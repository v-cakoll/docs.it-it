---
title: 'Procedura: Popolare le raccolte di oggetti da più origini (LINQ)'
ms.date: 06/22/2018
ms.assetid: 63062a22-e6a9-42c0-b357-c7c965f58f33
ms.openlocfilehash: 9c6d8ff5165bf886d8aad87b64305819e65361ab
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396519"
---
# <a name="how-to-populate-object-collections-from-multiple-sources-linq-visual-basic"></a>Procedura: popolare raccolte di oggetti da più origini (LINQ) (Visual Basic)

In questo esempio viene illustrato come unire dati da origini diverse in una sequenza di tipi nuovi.

> [!NOTE]
> Non provare a creare un join di dati in memoria o nel file system con dati che sono ancora in un database. Questi join tra domini possono generare risultati non definiti a causa dei diversi modi in cui vengono definite le operazioni di join per le query di database e per altri tipi di origini. È anche possibile che tale operazione possa generare un'eccezione di memoria insufficiente se la quantità di dati nel database è piuttosto grande. Per creare un join di dati di un database con i dati in memoria, chiamare prima `ToList` o `ToArray` nella query di database e quindi creare il join nella raccolta restituita.

## <a name="to-create-the-data-file"></a>Per creare il file di dati

- Copiare i file names. csv e scores. csv nella cartella del progetto, come descritto in [procedura: aggiungere contenuto da file non analoghi (LINQ) (Visual Basic)](how-to-join-content-from-dissimilar-files-linq.md).

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come usare un tipo denominato `Student` per archiviare i dati uniti da due raccolte di stringhe in memoria che simulano i dati del foglio di calcolo in formato CSV. La prima raccolta di stringhe rappresenta i nomi e gli ID degli studenti e la seconda raccolta rappresenta gli ID degli studenti, nella prima colonna, e i punteggi di quattro esami. L'ID viene usato come chiave esterna.

```vb
Imports System.Collections.Generic
Imports System.Linq

Class Student
    Public FirstName As String
    Public LastName As String
    Public ID As Integer
    Public ExamScores As List(Of Integer)
End Class

Class PopulateCollection

    Shared Sub Main()

        ' Merge content from spreadsheets into a list of Student objects.

        ' These data files are defined in How to: Join Content from
        ' Dissimilar Files (LINQ).

        ' Each line of names.csv consists of a last name, a first name, and an
        ' ID number, separated by commas. For example, Omelchenko,Svetlana,111
        Dim names As String() = System.IO.File.ReadAllLines("../../../names.csv")

        ' Each line of scores.csv consists of an ID number and four test
        ' scores, separated by commas. For example, 111, 97, 92, 81, 60
        Dim scores As String() = System.IO.File.ReadAllLines("../../../scores.csv")

        ' The following query merges the content of two dissimilar spreadsheets
        ' based on common ID values.
        ' Multiple From clauses are used instead of a Join clause
        ' in order to store the results of scoreLine.Split.
        ' Note the dynamic creation of a list of integers for the
        ' ExamScores member. The first item is skipped in the split string
        ' because it is the student ID, not an exam score.
        Dim queryNamesScores = From nameLine In names
                          Let splitName = nameLine.Split(New Char() {","})
                          From scoreLine In scores
                          Let splitScoreLine = scoreLine.Split(New Char() {","})
                          Where Convert.ToInt32(splitName(2)) = Convert.ToInt32(splitScoreLine(0))
                          Select New Student() With {
                               .FirstName = splitName(1), .LastName = splitName(0), .ID = splitName(2),
                               .ExamScores = (From scoreAsText In splitScoreLine Skip 1
                                             Select Convert.ToInt32(scoreAsText)).ToList()}

        ' Optional. Store the query results for faster access in future
        ' queries. This could be useful with very large data files.
        Dim students As List(Of Student) = queryNamesScores.ToList()

        ' Display each student's name and exam score average.
        For Each s In students
            Console.WriteLine("The average score of " & s.FirstName & " " &
                              s.LastName & " is " & s.ExamScores.Average())
        Next

        ' Keep console window open in debug mode.
        Console.WriteLine("Press any key to exit.")
        Console.ReadKey()
    End Sub
End Class

' Output:
' The average score of Svetlana Omelchenko is 82.5
' The average score of Claire O'Donnell is 72.25
' The average score of Sven Mortensen is 84.5
' The average score of Cesar Garcia is 88.25
' The average score of Debra Garcia is 67
' The average score of Fadi Fakhouri is 92.25
' The average score of Hanying Feng is 88
' The average score of Hugo Garcia is 85.75
' The average score of Lance Tucker is 81.75
' The average score of Terry Adams is 85.25
' The average score of Eugene Zabokritski is 83
' The average score of Michael Tucker is 92
```

Nella clausola [SELECT clausola](../../../language-reference/queries/select-clause.md) viene utilizzato un inizializzatore di oggetto per creare un'istanza di ogni nuovo `Student` oggetto utilizzando i dati delle due origini.

Se non è necessario archiviare i risultati della query, può essere più utile usare i tipi anonimi rispetto ai tipi denominati. I tipi denominati sono necessari se si passano i risultati della query al di fuori del metodo in cui viene eseguita la query. Nell'esempio seguente viene eseguita la stessa attività dell'esempio precedente, ma vengono usati i tipi anonimi anziché i tipi denominati:

```vb
' Merge the data by using an anonymous type.
' Note the dynamic creation of a list of integers for the
' ExamScores member. We skip 1 because the first string
' in the array is the student ID, not an exam score.
Dim queryNamesScores2 =
    From nameLine In names
    Let splitName = nameLine.Split(New Char() {","})
    From scoreLine In scores
    Let splitScoreLine = scoreLine.Split(New Char() {","})
    Where Convert.ToInt32(splitName(2)) = Convert.ToInt32(splitScoreLine(0))
    Select New With
           {.Last = splitName(0),
            .First = splitName(1),
            .ExamScores = (From scoreAsText In splitScoreLine Skip 1
                           Select Convert.ToInt32(scoreAsText)).ToList()}

' Display each student's name and exam score average.
For Each s In queryNamesScores2
    Console.WriteLine("The average score of " & s.First & " " &
                      s.Last & " is " & s.ExamScores.Average())
Next
```

## <a name="see-also"></a>Vedere anche

- [LINQ and Strings (Visual Basic)](linq-and-strings.md) (LINQ e le stringhe (Visual Basic))
