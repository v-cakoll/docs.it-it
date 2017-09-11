---
title: LINQ e le directory del File (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 159fd5c3-3926-4071-ae78-d8e423287eb7
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b9e814c9e9f8519522f288657d6940b07a0b3094
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="linq-and-file-directories-visual-basic"></a><span data-ttu-id="0eb0b-102">Directory di File (Visual Basic) e LINQ</span><span class="sxs-lookup"><span data-stu-id="0eb0b-102">LINQ and File Directories (Visual Basic)</span></span>
<span data-ttu-id="0eb0b-103">Molte operazioni del file system sono essenzialmente query e pertanto sono particolarmente adatte per l'approccio LINQ.</span><span class="sxs-lookup"><span data-stu-id="0eb0b-103">Many file system operations are essentially queries and are therefore well-suited to the LINQ approach.</span></span>  
  
 <span data-ttu-id="0eb0b-104">Si noti che le query in questa sezione non distruttiva.</span><span class="sxs-lookup"><span data-stu-id="0eb0b-104">Note that the queries in this section are non-destructive.</span></span> <span data-ttu-id="0eb0b-105">Non vengono utilizzati per modificare il contenuto del file originali o delle cartelle.</span><span class="sxs-lookup"><span data-stu-id="0eb0b-105">They are not used to change the contents of the original files or folders.</span></span> <span data-ttu-id="0eb0b-106">Si basa la regola che le query non dovrebbero causare effetti collaterali.</span><span class="sxs-lookup"><span data-stu-id="0eb0b-106">This follows the rule that queries should not cause any side-effects.</span></span> <span data-ttu-id="0eb0b-107">In generale, qualsiasi codice (incluse le query che eseguono creano, aggiornamento ed eliminazione operatori) che vengono modificati i dati di origine deve essere mantenuto separato dal codice che esegue solo una query dei dati.</span><span class="sxs-lookup"><span data-stu-id="0eb0b-107">In general, any code (including queries that perform create / update / delete operators) that modifies source data should be kept separate from the code that just queries the data.</span></span>  
  
 <span data-ttu-id="0eb0b-108">Questa sezione contiene i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="0eb0b-108">This section contains the following topics:</span></span>  
  
 [<span data-ttu-id="0eb0b-109">Procedura: eseguire una Query per i file con un attributo specificato o un nome (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0eb0b-109">How to: Query for Files with a Specified Attribute or Name (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)  
 <span data-ttu-id="0eb0b-110">Viene illustrato come cercare file esaminando una o più proprietà del relativo <xref:System.IO.FileInfo>oggetto.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="0eb0b-110">Shows how to search for files by examining one or more properties of its <xref:System.IO.FileInfo> object.</span></span>  
  
 [<span data-ttu-id="0eb0b-111">Procedura: raggruppare i file per estensione (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0eb0b-111">How to: Group Files by Extension (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)  
 <span data-ttu-id="0eb0b-112">Viene illustrato come restituire gruppi di <xref:System.IO.FileInfo>oggetto in base all'estensione di file.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="0eb0b-112">Shows how to return groups of <xref:System.IO.FileInfo> object based on their file name extension.</span></span>  
  
 [<span data-ttu-id="0eb0b-113">Procedura: eseguire una Query per il numero totale di byte in un Set di cartelle (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0eb0b-113">How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)  
 <span data-ttu-id="0eb0b-114">Viene illustrato come restituire il numero totale di byte in tutti i file in una struttura di directory specificato.</span><span class="sxs-lookup"><span data-stu-id="0eb0b-114">Shows how to return the total number of bytes in all the files in a specified directory tree.</span></span>  
  
 <span data-ttu-id="0eb0b-115">[Procedura: confrontare il contenuto di due cartelle (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-compare-the-contents-of-two-folders-linq.md)s</span><span class="sxs-lookup"><span data-stu-id="0eb0b-115">[How to: Compare the Contents of Two Folders (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-compare-the-contents-of-two-folders-linq.md)s</span></span>  
 <span data-ttu-id="0eb0b-116">Viene illustrato come restituire tutti i file presenti in due cartelle specifiche e anche tutti i file presenti in una cartella, ma non l'altro.</span><span class="sxs-lookup"><span data-stu-id="0eb0b-116">Shows how to return all the files that are present in two specified folders, and also all the files that are present in one folder but not the other.</span></span>  
  
 [<span data-ttu-id="0eb0b-117">Procedura: eseguire una Query per il più grande o più file in una struttura di Directory (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0eb0b-117">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)  
 <span data-ttu-id="0eb0b-118">Viene illustrato come ripristinare il file massimo o minimo o un numero specificato di file, in una struttura di directory.</span><span class="sxs-lookup"><span data-stu-id="0eb0b-118">Shows how to return the largest or smallest file, or a specified number of files, in a directory tree.</span></span>  
  
 [<span data-ttu-id="0eb0b-119">Procedura: eseguire una Query per i file duplicati in una struttura di Directory (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0eb0b-119">How to: Query for Duplicate Files in a Directory Tree (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md)  
 <span data-ttu-id="0eb0b-120">Viene illustrato come raggruppare tutti i nomi file che si verificano in più di una posizione in una struttura di directory specificato.</span><span class="sxs-lookup"><span data-stu-id="0eb0b-120">Shows how to group for all file names that occur in more than one location in a specified directory tree.</span></span> <span data-ttu-id="0eb0b-121">Viene inoltre illustrato come eseguire confronti più complessi basati su un operatore di confronto personalizzato.</span><span class="sxs-lookup"><span data-stu-id="0eb0b-121">Also shows how to perform more complex comparisons based on a custom comparer.</span></span>  
  
 [<span data-ttu-id="0eb0b-122">Procedura: eseguire Query sul contenuto dei file in una cartella (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0eb0b-122">How to: Query the Contents of Files in a Folder (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-the-contents-of-files-in-a-folder-linq.md)  
 <span data-ttu-id="0eb0b-123">Viene illustrato come scorrere le cartelle in una struttura ad albero, aprire ogni file e il contenuto del file di query.</span><span class="sxs-lookup"><span data-stu-id="0eb0b-123">Shows how to iterate through folders in a tree, open each file, and query the file's contents.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="0eb0b-124">Commenti</span><span class="sxs-lookup"><span data-stu-id="0eb0b-124">Comments</span></span>  
 <span data-ttu-id="0eb0b-125">Esiste un livello di complessità per la creazione di un'origine dati che rappresenta il contenuto del file system e gestisce correttamente le eccezioni in modo accurato.</span><span class="sxs-lookup"><span data-stu-id="0eb0b-125">There is some complexity involved in creating a data source that accurately represents the contents of the file system and handles exceptions gracefully.</span></span> <span data-ttu-id="0eb0b-126">Negli esempi inclusi in questa sezione creano un insieme di snapshot <xref:System.IO.FileInfo>gli oggetti che rappresentano tutti i file nella cartella principale specificata e tutte le relative sottocartelle.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="0eb0b-126">The examples in this section create a snapshot collection of <xref:System.IO.FileInfo> objects that represents all the files under a specified root folder and all its subfolders.</span></span> <span data-ttu-id="0eb0b-127">Lo stato di ogni <xref:System.IO.FileInfo>può cambiare nel tempo tra l'inizio e la fine dell'esecuzione di una query.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="0eb0b-127">The actual state of each <xref:System.IO.FileInfo> may change in the time between when you begin and end executing a query.</span></span> <span data-ttu-id="0eb0b-128">Ad esempio, è possibile creare un elenco di <xref:System.IO.FileInfo>degli oggetti da utilizzare come origine dati.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="0eb0b-128">For example, you can create a list of <xref:System.IO.FileInfo> objects to use as a data source.</span></span> <span data-ttu-id="0eb0b-129">Se si tenta di accedere il `Length` proprietà in una query, il <xref:System.IO.FileInfo>oggetto tenterà di accedere al file system per aggiornare il valore di `Length`.</xref:System.IO.FileInfo></span><span class="sxs-lookup"><span data-stu-id="0eb0b-129">If you try to access the `Length` property in a query, the <xref:System.IO.FileInfo> object will try to access the file system to update the value of `Length`.</span></span> <span data-ttu-id="0eb0b-130">Se il file non esiste più, si otterrà un <xref:System.IO.FileNotFoundException>nella query, anche se non si è eseguendo una query direttamente nel file system.</xref:System.IO.FileNotFoundException></span><span class="sxs-lookup"><span data-stu-id="0eb0b-130">If the file no longer exists, you will get a <xref:System.IO.FileNotFoundException> in your query, even though you are not querying the file system directly.</span></span> <span data-ttu-id="0eb0b-131">Alcune query in questa sezione utilizzare un metodo separato che utilizza queste particolari eccezioni in determinati casi.</span><span class="sxs-lookup"><span data-stu-id="0eb0b-131">Some queries in this section use a separate method that consumes these particular exceptions in certain cases.</span></span> <span data-ttu-id="0eb0b-132">Un'altra opzione consiste nel mantenere l'origine dati aggiornata in modo dinamico utilizzando <xref:System.IO.FileSystemWatcher>.</xref:System.IO.FileSystemWatcher></span><span class="sxs-lookup"><span data-stu-id="0eb0b-132">Another option is to keep your data source updated dynamically by using the <xref:System.IO.FileSystemWatcher>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eb0b-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0eb0b-133">See Also</span></span>  
 [<span data-ttu-id="0eb0b-134">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0eb0b-134">LINQ to Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
