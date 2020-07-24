---
title: Come popolare le raccolte di oggetti da più origini (LINQ) (C#)
description: Informazioni su come unire dati da origini diverse in una sequenza di nuovi tipi usando LINQ in C#. In questi esempi vengono utilizzati tipi anonimi e denominati.
ms.date: 06/12/2018
ms.assetid: 8ad7d480-b46c-4ccc-8c57-76f2d04ccc6d
ms.openlocfilehash: 9dc9f98ae09e0fe3437b5d2ccab32b3dbcd93714
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104719"
---
# <a name="how-to-populate-object-collections-from-multiple-sources-linq-c"></a>Come popolare le raccolte di oggetti da più origini (LINQ) (C#)

In questo esempio viene illustrato come unire dati da origini diverse in una sequenza di tipi nuovi.

> [!NOTE]
> Non provare a creare un join di dati in memoria o nel file system con dati che sono ancora in un database. Questi join tra domini possono generare risultati non definiti a causa dei diversi modi in cui vengono definite le operazioni di join per le query di database e per altri tipi di origini. È anche possibile che tale operazione possa generare un'eccezione di memoria insufficiente se la quantità di dati nel database è piuttosto grande. Per creare un join di dati di un database con i dati in memoria, chiamare prima `ToList` o `ToArray` nella query di database e quindi creare il join nella raccolta restituita.

## <a name="to-create-the-data-file"></a>Per creare il file di dati

Copiare i file names.csv e scores.csv nella cartella del progetto, come descritto in [come unire il contenuto da file non analoghi (LINQ) (C#)](./how-to-join-content-from-dissimilar-files-linq.md).

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come usare un tipo denominato `Student` per archiviare i dati uniti da due raccolte di stringhe in memoria che simulano i dati del foglio di calcolo in formato CSV. La prima raccolta di stringhe rappresenta i nomi e gli ID degli studenti e la seconda raccolta rappresenta gli ID degli studenti, nella prima colonna, e i punteggi di quattro esami. L'ID viene usato come chiave esterna.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;

class Student
{
    public string FirstName { get; set; }
    public string LastName { get; set; }
    public int ID { get; set; }
    public List<int> ExamScores { get; set; }
}

class PopulateCollection
{
    static void Main()
    {
        // These data files are defined in How to join content from
        // dissimilar files (LINQ).

        // Each line of names.csv consists of a last name, a first name, and an
        // ID number, separated by commas. For example, Omelchenko,Svetlana,111
        string[] names = System.IO.File.ReadAllLines(@"../../../names.csv");

        // Each line of scores.csv consists of an ID number and four test
        // scores, separated by commas. For example, 111, 97, 92, 81, 60
        string[] scores = System.IO.File.ReadAllLines(@"../../../scores.csv");

        // Merge the data sources using a named type.
        // var could be used instead of an explicit type. Note the dynamic
        // creation of a list of ints for the ExamScores member. The first item
        // is skipped in the split string because it is the student ID,
        // not an exam score.
        IEnumerable<Student> queryNamesScores =
            from nameLine in names
            let splitName = nameLine.Split(',')
            from scoreLine in scores
            let splitScoreLine = scoreLine.Split(',')
            where Convert.ToInt32(splitName[2]) == Convert.ToInt32(splitScoreLine[0])
            select new Student()
            {
                FirstName = splitName[0],
                LastName = splitName[1],
                ID = Convert.ToInt32(splitName[2]),
                ExamScores = (from scoreAsText in splitScoreLine.Skip(1)
                              select Convert.ToInt32(scoreAsText)).
                              ToList()
            };

        // Optional. Store the newly created student objects in memory
        // for faster access in future queries. This could be useful with
        // very large data files.
        List<Student> students = queryNamesScores.ToList();

        // Display each student's name and exam score average.
        foreach (var student in students)
        {
            Console.WriteLine("The average score of {0} {1} is {2}.",
                student.FirstName, student.LastName,
                student.ExamScores.Average());
        }

        //Keep console window open in debug mode
        Console.WriteLine("Press any key to exit.");
        Console.ReadKey();
    }
}
/* Output:
    The average score of Omelchenko Svetlana is 82.5.
    The average score of O'Donnell Claire is 72.25.
    The average score of Mortensen Sven is 84.5.
    The average score of Garcia Cesar is 88.25.
    The average score of Garcia Debra is 67.
    The average score of Fakhouri Fadi is 92.25.
    The average score of Feng Hanying is 88.
    The average score of Garcia Hugo is 85.75.
    The average score of Tucker Lance is 81.75.
    The average score of Adams Terry is 85.25.
    The average score of Zabokritski Eugene is 83.
    The average score of Tucker Michael is 92.
 */
```

Nella clausola [select](../../../language-reference/keywords/select-clause.md) viene usato un inizializzatore di oggetto per creare un'istanza di ogni nuovo oggetto `Student` con i dati delle due origini.

Se non è necessario archiviare i risultati della query, può essere più utile usare i tipi anonimi rispetto ai tipi denominati. I tipi denominati sono necessari se si passano i risultati della query al di fuori del metodo in cui viene eseguita la query. Nell'esempio seguente viene eseguita la stessa attività dell'esempio precedente, ma vengono usati i tipi anonimi al posto dei tipi denominati:

```csharp
// Merge the data sources by using an anonymous type.
// Note the dynamic creation of a list of ints for the
// ExamScores member. We skip 1 because the first string
// in the array is the student ID, not an exam score.
var queryNamesScores2 =
    from nameLine in names
    let splitName = nameLine.Split(',')
    from scoreLine in scores
    let splitScoreLine = scoreLine.Split(',')
    where Convert.ToInt32(splitName[2]) == Convert.ToInt32(splitScoreLine[0])
    select new
    {
        First = splitName[0],
        Last = splitName[1],
        ExamScores = (from scoreAsText in splitScoreLine.Skip(1)
                      select Convert.ToInt32(scoreAsText))
                      .ToList()
    };

// Display each student's name and exam score average.
foreach (var student in queryNamesScores2)
{
    Console.WriteLine("The average score of {0} {1} is {2}.",
        student.First, student.Last, student.ExamScores.Average());
}
```

## <a name="see-also"></a>Vedere anche

- [LINQ e stringhe (C#)](./linq-and-strings.md)
- [Inizializzatori di oggetto e di raccolta](../../classes-and-structs/object-and-collection-initializers.md)
- [Tipi anonimi](../../classes-and-structs/anonymous-types.md)
