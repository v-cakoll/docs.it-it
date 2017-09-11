---
title: Directory di file e LINQ (C#)
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
ms.assetid: b66c55e4-0f72-44e5-b086-519f9962335c
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
ms.openlocfilehash: e7324e3b1d165bfe7ef477fa73bac5d3e7735dc5
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="linq-and-file-directories-c"></a><span data-ttu-id="85e6d-102">Directory di file e LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="85e6d-102">LINQ and File Directories (C#)</span></span>
<span data-ttu-id="85e6d-103">Molte operazioni del file system sono essenzialmente query e quindi particolarmente adatte all'approccio LINQ.</span><span class="sxs-lookup"><span data-stu-id="85e6d-103">Many file system operations are essentially queries and are therefore well-suited to the LINQ approach.</span></span>  
  
 <span data-ttu-id="85e6d-104">Si noti che le query in questa sezione sono non distruttive.</span><span class="sxs-lookup"><span data-stu-id="85e6d-104">Note that the queries in this section are non-destructive.</span></span> <span data-ttu-id="85e6d-105">Non vengono usate per modificare il contenuto dei file o delle cartelle originali.</span><span class="sxs-lookup"><span data-stu-id="85e6d-105">They are not used to change the contents of the original files or folders.</span></span> <span data-ttu-id="85e6d-106">Ne consegue la regola per cui le query non dovrebbero causare effetti collaterali.</span><span class="sxs-lookup"><span data-stu-id="85e6d-106">This follows the rule that queries should not cause any side-effects.</span></span> <span data-ttu-id="85e6d-107">In generale, il codice (incluse le query che eseguono operatori create/update/delete) che modifica i dati di origine deve essere mantenuto separato dal codice che esegue esclusivamente query sui dati.</span><span class="sxs-lookup"><span data-stu-id="85e6d-107">In general, any code (including queries that perform create / update / delete operators) that modifies source data should be kept separate from the code that just queries the data.</span></span>  
  
 <span data-ttu-id="85e6d-108">Questa sezione contiene i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="85e6d-108">This section contains the following topics:</span></span>  
  
 [<span data-ttu-id="85e6d-109">Procedura: Eseguire una query per trovare i file con un attributo o un nome specifico (C#)</span><span class="sxs-lookup"><span data-stu-id="85e6d-109">How to: Query for Files with a Specified Attribute or Name (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)  
 <span data-ttu-id="85e6d-110">La procedura illustra come cercare file esaminando una o più proprietà del relativo oggetto <xref:System.IO.FileInfo>.</span><span class="sxs-lookup"><span data-stu-id="85e6d-110">Shows how to search for files by examining one or more properties of its <xref:System.IO.FileInfo> object.</span></span>  
  
 [<span data-ttu-id="85e6d-111">Procedura: Raggruppare file per estensione (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="85e6d-111">How to: Group Files by Extension (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)  
 <span data-ttu-id="85e6d-112">La procedura illustra come restituire gruppi dell'oggetto <xref:System.IO.FileInfo> in base all'estensione del file.</span><span class="sxs-lookup"><span data-stu-id="85e6d-112">Shows how to return groups of <xref:System.IO.FileInfo> object based on their file name extension.</span></span>  
  
 [<span data-ttu-id="85e6d-113">Procedura: Eseguire una query per trovare il numero totale di byte in un set di cartelle (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="85e6d-113">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq.md)  
 <span data-ttu-id="85e6d-114">La procedura illustra come restituire il numero totale di byte in tutti i file all'interno di un albero di directory specificato.</span><span class="sxs-lookup"><span data-stu-id="85e6d-114">Shows how to return the total number of bytes in all the files in a specified directory tree.</span></span>  
  
 <span data-ttu-id="85e6d-115">[Procedura: Confrontare il contenuto di due cartelle (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-compare-the-contents-of-two-folders-linq.md)</span><span class="sxs-lookup"><span data-stu-id="85e6d-115">[How to: Compare the Contents of Two Folders (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-compare-the-contents-of-two-folders-linq.md)s</span></span>  
 <span data-ttu-id="85e6d-116">La procedura illustra come restituire tutti i file presenti in due cartelle specifiche e tutti i file presenti in una cartella, ma non nell'altra.</span><span class="sxs-lookup"><span data-stu-id="85e6d-116">Shows how to return all the files that are present in two specified folders, and also all the files that are present in one folder but not the other.</span></span>  
  
 [<span data-ttu-id="85e6d-117">Procedura: eseguire una query per trovare il file o i file più grandi in un albero di directory (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="85e6d-117">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq.md)  
 <span data-ttu-id="85e6d-118">La procedura illustra come ripristinare il file più grande, il file più piccolo o un numero specificato di file in un albero di directory.</span><span class="sxs-lookup"><span data-stu-id="85e6d-118">Shows how to return the largest or smallest file, or a specified number of files, in a directory tree.</span></span>  
  
 [<span data-ttu-id="85e6d-119">Procedura: Eseguire una query per trovare i file duplicati in un albero di directory (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="85e6d-119">How to: Query for Duplicate Files in a Directory Tree (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md)  
 <span data-ttu-id="85e6d-120">La procedura illustra come raggruppare tutti i nomi file che si verificano in più di una posizione all'interno di un albero di directory specificato.</span><span class="sxs-lookup"><span data-stu-id="85e6d-120">Shows how to group for all file names that occur in more than one location in a specified directory tree.</span></span> <span data-ttu-id="85e6d-121">Viene anche illustrato come eseguire confronti più complessi basati su un operatore di confronto personalizzato.</span><span class="sxs-lookup"><span data-stu-id="85e6d-121">Also shows how to perform more complex comparisons based on a custom comparer.</span></span>  
  
 [<span data-ttu-id="85e6d-122">Procedura: eseguire una query sul contenuto dei file in una cartella (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="85e6d-122">How to: Query the Contents of Files in a Folder (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-the-contents-of-files-in-a-folder-lin.md)  
 <span data-ttu-id="85e6d-123">La procedura illustra come eseguire l'iterazione nelle cartelle in un albero, aprire ogni file ed eseguire query sul contenuto del file.</span><span class="sxs-lookup"><span data-stu-id="85e6d-123">Shows how to iterate through folders in a tree, open each file, and query the file's contents.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="85e6d-124">Commenti</span><span class="sxs-lookup"><span data-stu-id="85e6d-124">Comments</span></span>  
 <span data-ttu-id="85e6d-125">La creazione di un'origine dati che rappresenta accuratamente il contenuto del file system e gestisce correttamente le eccezioni comporta un certo livello di complessità.</span><span class="sxs-lookup"><span data-stu-id="85e6d-125">There is some complexity involved in creating a data source that accurately represents the contents of the file system and handles exceptions gracefully.</span></span> <span data-ttu-id="85e6d-126">Negli esempi riportati in questa sezione viene creata una raccolta di snapshot di oggetti <xref:System.IO.FileInfo>, che rappresenta tutti i file in una cartella radice specificata e in tutte le relative sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="85e6d-126">The examples in this section create a snapshot collection of <xref:System.IO.FileInfo> objects that represents all the files under a specified root folder and all its subfolders.</span></span> <span data-ttu-id="85e6d-127">Lo stato effettivo di ogni <xref:System.IO.FileInfo> può cambiare nel tempo tra l'inizio e la fine dell'esecuzione di una query.</span><span class="sxs-lookup"><span data-stu-id="85e6d-127">The actual state of each <xref:System.IO.FileInfo> may change in the time between when you begin and end executing a query.</span></span> <span data-ttu-id="85e6d-128">Ad esempio, è possibile creare un elenco di oggetti <xref:System.IO.FileInfo> da usare come origine dati.</span><span class="sxs-lookup"><span data-stu-id="85e6d-128">For example, you can create a list of <xref:System.IO.FileInfo> objects to use as a data source.</span></span> <span data-ttu-id="85e6d-129">Se si tenta di accedere alla proprietà `Length` in una query, l'oggetto <xref:System.IO.FileInfo> tenterà di accedere al file system per aggiornare il valore di `Length`.</span><span class="sxs-lookup"><span data-stu-id="85e6d-129">If you try to access the `Length` property in a query, the <xref:System.IO.FileInfo> object will try to access the file system to update the value of `Length`.</span></span> <span data-ttu-id="85e6d-130">Se il file non esiste più, nella query si otterrà un'eccezione <xref:System.IO.FileNotFoundException>, anche se non si sta eseguendo una query direttamente nel file system.</span><span class="sxs-lookup"><span data-stu-id="85e6d-130">If the file no longer exists, you will get a <xref:System.IO.FileNotFoundException> in your query, even though you are not querying the file system directly.</span></span> <span data-ttu-id="85e6d-131">Alcune query in questa sezione usano un metodo separato che impiega queste particolari eccezioni in determinati casi.</span><span class="sxs-lookup"><span data-stu-id="85e6d-131">Some queries in this section use a separate method that consumes these particular exceptions in certain cases.</span></span> <span data-ttu-id="85e6d-132">Un'altra opzione consiste nel mantenere l'origine dati aggiornata in modo dinamico tramite <xref:System.IO.FileSystemWatcher>.</span><span class="sxs-lookup"><span data-stu-id="85e6d-132">Another option is to keep your data source updated dynamically by using the <xref:System.IO.FileSystemWatcher>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85e6d-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85e6d-133">See Also</span></span>  
 [<span data-ttu-id="85e6d-134">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="85e6d-134">LINQ to Objects (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)

