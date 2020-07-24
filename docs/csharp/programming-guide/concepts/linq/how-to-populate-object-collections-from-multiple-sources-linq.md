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
# <a name="how-to-populate-object-collections-from-multiple-sources-linq-c"></a><span data-ttu-id="cb46e-104">Come popolare le raccolte di oggetti da più origini (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="cb46e-104">How to populate object collections from multiple sources (LINQ) (C#)</span></span>

<span data-ttu-id="cb46e-105">In questo esempio viene illustrato come unire dati da origini diverse in una sequenza di tipi nuovi.</span><span class="sxs-lookup"><span data-stu-id="cb46e-105">This example shows how to merge data from different sources into a sequence of new types.</span></span>

> [!NOTE]
> <span data-ttu-id="cb46e-106">Non provare a creare un join di dati in memoria o nel file system con dati che sono ancora in un database.</span><span class="sxs-lookup"><span data-stu-id="cb46e-106">Don't try to join in-memory data or data in the file system with data that is still in a database.</span></span> <span data-ttu-id="cb46e-107">Questi join tra domini possono generare risultati non definiti a causa dei diversi modi in cui vengono definite le operazioni di join per le query di database e per altri tipi di origini.</span><span class="sxs-lookup"><span data-stu-id="cb46e-107">Such cross-domain joins can yield undefined results because of different ways in which join operations might be defined for database queries and other types of sources.</span></span> <span data-ttu-id="cb46e-108">È anche possibile che tale operazione possa generare un'eccezione di memoria insufficiente se la quantità di dati nel database è piuttosto grande.</span><span class="sxs-lookup"><span data-stu-id="cb46e-108">Additionally, there is a risk that such an operation could cause an out-of-memory exception if the amount of data in the database is large enough.</span></span> <span data-ttu-id="cb46e-109">Per creare un join di dati di un database con i dati in memoria, chiamare prima `ToList` o `ToArray` nella query di database e quindi creare il join nella raccolta restituita.</span><span class="sxs-lookup"><span data-stu-id="cb46e-109">To join data from a database to in-memory data, first call `ToList` or `ToArray` on the database query, and then perform the join on the returned collection.</span></span>

## <a name="to-create-the-data-file"></a><span data-ttu-id="cb46e-110">Per creare il file di dati</span><span class="sxs-lookup"><span data-stu-id="cb46e-110">To create the data file</span></span>

<span data-ttu-id="cb46e-111">Copiare i file names.csv e scores.csv nella cartella del progetto, come descritto in [come unire il contenuto da file non analoghi (LINQ) (C#)](./how-to-join-content-from-dissimilar-files-linq.md).</span><span class="sxs-lookup"><span data-stu-id="cb46e-111">Copy the names.csv and scores.csv files into your project folder, as described in [How to join content from dissimilar files (LINQ) (C#)](./how-to-join-content-from-dissimilar-files-linq.md).</span></span>

## <a name="example"></a><span data-ttu-id="cb46e-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="cb46e-112">Example</span></span>

<span data-ttu-id="cb46e-113">Nell'esempio seguente viene illustrato come usare un tipo denominato `Student` per archiviare i dati uniti da due raccolte di stringhe in memoria che simulano i dati del foglio di calcolo in formato CSV.</span><span class="sxs-lookup"><span data-stu-id="cb46e-113">The following example shows how to use a named type `Student` to store merged data from two in-memory collections of strings that simulate spreadsheet data in .csv format.</span></span> <span data-ttu-id="cb46e-114">La prima raccolta di stringhe rappresenta i nomi e gli ID degli studenti e la seconda raccolta rappresenta gli ID degli studenti, nella prima colonna, e i punteggi di quattro esami.</span><span class="sxs-lookup"><span data-stu-id="cb46e-114">The first collection of strings represents the student names and IDs, and the second collection represents the student ID (in the first column) and four exam scores.</span></span> <span data-ttu-id="cb46e-115">L'ID viene usato come chiave esterna.</span><span class="sxs-lookup"><span data-stu-id="cb46e-115">The ID is used as the foreign key.</span></span>

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

<span data-ttu-id="cb46e-116">Nella clausola [select](../../../language-reference/keywords/select-clause.md) viene usato un inizializzatore di oggetto per creare un'istanza di ogni nuovo oggetto `Student` con i dati delle due origini.</span><span class="sxs-lookup"><span data-stu-id="cb46e-116">In the [select](../../../language-reference/keywords/select-clause.md) clause, an object initializer is used to instantiate each new `Student` object by using the data from the two sources.</span></span>

<span data-ttu-id="cb46e-117">Se non è necessario archiviare i risultati della query, può essere più utile usare i tipi anonimi rispetto ai tipi denominati.</span><span class="sxs-lookup"><span data-stu-id="cb46e-117">If you don't have to store the results of a query, anonymous types can be more convenient than named types.</span></span> <span data-ttu-id="cb46e-118">I tipi denominati sono necessari se si passano i risultati della query al di fuori del metodo in cui viene eseguita la query.</span><span class="sxs-lookup"><span data-stu-id="cb46e-118">Named types are required if you pass the query results outside the method in which the query is executed.</span></span> <span data-ttu-id="cb46e-119">Nell'esempio seguente viene eseguita la stessa attività dell'esempio precedente, ma vengono usati i tipi anonimi al posto dei tipi denominati:</span><span class="sxs-lookup"><span data-stu-id="cb46e-119">The following example executes the same task as the previous example, but uses anonymous types instead of named types:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="cb46e-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb46e-120">See also</span></span>

- [<span data-ttu-id="cb46e-121">LINQ e stringhe (C#)</span><span class="sxs-lookup"><span data-stu-id="cb46e-121">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
- [<span data-ttu-id="cb46e-122">Inizializzatori di oggetto e di raccolta</span><span class="sxs-lookup"><span data-stu-id="cb46e-122">Object and Collection Initializers</span></span>](../../classes-and-structs/object-and-collection-initializers.md)
- [<span data-ttu-id="cb46e-123">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="cb46e-123">Anonymous Types</span></span>](../../classes-and-structs/anonymous-types.md)
