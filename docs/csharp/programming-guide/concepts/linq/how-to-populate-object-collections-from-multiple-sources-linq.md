---
title: "Procedura: Popolare le raccolte di oggetti da più origini (LINQ) (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 8ad7d480-b46c-4ccc-8c57-76f2d04ccc6d
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 384449bf8202c707b1c7f5a75445410bc6270907
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-populate-object-collections-from-multiple-sources-linq-c"></a><span data-ttu-id="fd714-102">Procedura: Popolare le raccolte di oggetti da più origini (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="fd714-102">How to: Populate Object Collections from Multiple Sources (LINQ) (C#)</span></span>
<span data-ttu-id="fd714-103">In questo esempio viene illustrato come unire dati da origini diverse in una sequenza di tipi nuovi.</span><span class="sxs-lookup"><span data-stu-id="fd714-103">This example shows how to merge data from different sources into a sequence of new types.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd714-104">Non tentare di creare un join di dati in memoria o nel file system con dati che sono ancora in un database.</span><span class="sxs-lookup"><span data-stu-id="fd714-104">Do not try to join in-memory data or data in the file system with data that is still in a database.</span></span> <span data-ttu-id="fd714-105">Questi join tra domini possono generare risultati non definiti a causa dei diversi modi in cui vengono definite le operazioni di join per le query di database e per altri tipi di origini.</span><span class="sxs-lookup"><span data-stu-id="fd714-105">Such cross-domain joins can yield undefined results because of different ways in which join operations might be defined for database queries and other types of sources.</span></span> <span data-ttu-id="fd714-106">È anche possibile che tale operazione possa generare un'eccezione di memoria insufficiente se la quantità di dati nel database è piuttosto grande.</span><span class="sxs-lookup"><span data-stu-id="fd714-106">Additionally, there is a risk that such an operation could cause an out-of-memory exception if the amount of data in the database is large enough.</span></span> <span data-ttu-id="fd714-107">Per creare un join di dati di un database con i dati in memoria, chiamare prima `ToList` o `ToArray` nella query di database e quindi creare il join nella raccolta restituita.</span><span class="sxs-lookup"><span data-stu-id="fd714-107">To join data from a database to in-memory data, first call `ToList` or `ToArray` on the database query, and then perform the join on the returned collection.</span></span>  
  
### <a name="to-create-the-data-file"></a><span data-ttu-id="fd714-108">Per creare il file di dati</span><span class="sxs-lookup"><span data-stu-id="fd714-108">To create the data file</span></span>  
  
-   <span data-ttu-id="fd714-109">Copiare i file names.csv e scores.csv nella cartella del progetto, come descritto in [Procedura: Creare un join da file non analoghi (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md).</span><span class="sxs-lookup"><span data-stu-id="fd714-109">Copy the names.csv and scores.csv files into your project folder, as described in [How to: Join Content from Dissimilar Files (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd714-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="fd714-110">Example</span></span>  
 <span data-ttu-id="fd714-111">Nell'esempio seguente viene illustrato come usare un tipo denominato `Student` per archiviare i dati uniti da due raccolte di stringhe in memoria che simulano i dati del foglio di calcolo in formato CSV.</span><span class="sxs-lookup"><span data-stu-id="fd714-111">The following example shows how to use a named type `Student` to store merged data from two in-memory collections of strings that simulate spreadsheet data in .csv format.</span></span> <span data-ttu-id="fd714-112">La prima raccolta di stringhe rappresenta i nomi e gli ID degli studenti e la seconda raccolta rappresenta gli ID degli studenti, nella prima colonna, e i punteggi di quattro esami.</span><span class="sxs-lookup"><span data-stu-id="fd714-112">The first collection of strings represents the student names and IDs, and the second collection represents the student ID (in the first column) and four exam scores.</span></span> <span data-ttu-id="fd714-113">L'ID viene usato come chiave esterna.</span><span class="sxs-lookup"><span data-stu-id="fd714-113">The ID is used as the foreign key.</span></span>  
  
```csharp  
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
        // These data files are defined in How to: Join Content from   
        // Dissimilar Files (LINQ).  
  
        // Each line of names.csv consists of a last name, a first name, and an  
        // ID number, separated by commas. For example, Omelchenko,Svetlana,111  
        string[] names = System.IO.File.ReadAllLines(@"../../../names.csv");  
  
        // Each line of scores.csv consists of an ID number and four test   
        // scores, separated by commas. For example, 111, 97, 92, 81, 60  
        string[] scores = System.IO.File.ReadAllLines(@"../../../scores.csv");  
  
        // Merge the data sources using a named type.  
        // var could be used instead of an explicit type. Note the dynamic  
        // creation of a list of ints for the ExamScores member. We skip   
        // the first item in the split string because it is the student ID,   
        // not an exam score.  
        IEnumerable<Student> queryNamesScores =  
            from nameLine in names  
            let splitName = nameLine.Split(',')  
            from scoreLine in scores  
            let splitScoreLine = scoreLine.Split(',')  
            where splitName[2] == splitScoreLine[0]  
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
  
 <span data-ttu-id="fd714-114">Nella clausola [select](../../../../csharp/language-reference/keywords/select-clause.md) viene usato un inizializzatore di oggetto per creare un'istanza di ogni nuovo oggetto `Student` con i dati delle due origini.</span><span class="sxs-lookup"><span data-stu-id="fd714-114">In the [select](../../../../csharp/language-reference/keywords/select-clause.md) clause, an object initializer is used to instantiate each new `Student` object by using the data from the two sources.</span></span>  
  
 <span data-ttu-id="fd714-115">Se non è necessario archiviare i risultati della query, può essere più utile usare i tipi anonimi rispetto ai tipi denominati.</span><span class="sxs-lookup"><span data-stu-id="fd714-115">If you do not have to store the results of a query, anonymous types can be more convenient than named types.</span></span> <span data-ttu-id="fd714-116">I tipi denominati sono necessari se si passano i risultati della query al di fuori del metodo in cui viene eseguita la query.</span><span class="sxs-lookup"><span data-stu-id="fd714-116">Named types are required if you pass the query results outside the method in which the query is executed.</span></span> <span data-ttu-id="fd714-117">Nell'esempio seguente viene eseguita la stessa attività dell'esempio precedente, ma vengono usati i tipi anonimi anziché i tipi denominati:</span><span class="sxs-lookup"><span data-stu-id="fd714-117">The following example performs the same task as the previous example, but uses anonymous types instead of named types:</span></span>  
  
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
    where splitName[2] == splitScoreLine[0]  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="fd714-118">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="fd714-118">Compiling the Code</span></span>  
 <span data-ttu-id="fd714-119">Creare un progetto che usi .NET Framework versione 3.5 o successiva con un riferimento a System.Core.dll e alle direttive `using` per gli spazi dei nomi System.Linq e System.IO.</span><span class="sxs-lookup"><span data-stu-id="fd714-119">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd714-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd714-120">See Also</span></span>  
 <span data-ttu-id="fd714-121">[LINQ e stringhe (C#)](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md) </span><span class="sxs-lookup"><span data-stu-id="fd714-121">[LINQ and Strings (C#)](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md) </span></span>  
 <span data-ttu-id="fd714-122">[Inizializzatori di oggetto e di insieme](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md) </span><span class="sxs-lookup"><span data-stu-id="fd714-122">[Object and Collection Initializers](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md) </span></span>  
 [<span data-ttu-id="fd714-123">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="fd714-123">Anonymous Types</span></span>](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)

