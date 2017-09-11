---
title: LINQ e stringhe (Visual Basic) | Documenti di Microsoft
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
ms.assetid: 75ddb201-d97a-4f98-8cdf-4ad51714529a
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 94e9627efb183c08bbb67a7e6e82df9132ebdef2
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="linq-and-strings-visual-basic"></a><span data-ttu-id="b09a8-102">LINQ e stringhe (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b09a8-102">LINQ and Strings (Visual Basic)</span></span>
<span data-ttu-id="b09a8-103">LINQ può essere utilizzato per eseguire query e trasformare stringhe e raccolte di stringhe.</span><span class="sxs-lookup"><span data-stu-id="b09a8-103">LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="b09a8-104">Può essere particolarmente utile con dati semistrutturati nei file di testo.</span><span class="sxs-lookup"><span data-stu-id="b09a8-104">It can be especially useful with semi-structured data in text files.</span></span> <span data-ttu-id="b09a8-105">Le query LINQ possono essere combinate con espressioni regolari e le funzioni stringa tradizionale.</span><span class="sxs-lookup"><span data-stu-id="b09a8-105">LINQ queries can be combined with traditional string functions and regular expressions.</span></span> <span data-ttu-id="b09a8-106">Ad esempio, è possibile utilizzare il <xref:System.String.Split%2A>o <xref:System.Text.RegularExpressions.Regex.Split%2A>per creare una matrice di stringhe che è possibile eseguire una query o modificare utilizzando LINQ.</xref:System.Text.RegularExpressions.Regex.Split%2A> </xref:System.String.Split%2A></span><span class="sxs-lookup"><span data-stu-id="b09a8-106">For example, you can use the <xref:System.String.Split%2A> or <xref:System.Text.RegularExpressions.Regex.Split%2A> method to create an array of strings that you can then query or modify by using LINQ.</span></span> <span data-ttu-id="b09a8-107">È possibile utilizzare il <xref:System.Text.RegularExpressions.Regex.IsMatch%2A>metodo il `where` clausola di una query LINQ.</xref:System.Text.RegularExpressions.Regex.IsMatch%2A></span><span class="sxs-lookup"><span data-stu-id="b09a8-107">You can use the <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> method in the `where` clause of a LINQ query.</span></span> <span data-ttu-id="b09a8-108">Ed è possibile utilizzare LINQ per eseguire una query o modificare il <xref:System.Text.RegularExpressions.MatchCollection>risultati restituiti da un'espressione regolare.</xref:System.Text.RegularExpressions.MatchCollection></span><span class="sxs-lookup"><span data-stu-id="b09a8-108">And you can use LINQ to query or modify the <xref:System.Text.RegularExpressions.MatchCollection> results returned by a regular expression.</span></span>  
  
 <span data-ttu-id="b09a8-109">È inoltre possibile utilizzare le tecniche descritte in questa sezione per trasformare dati semistrutturati testo in XML.</span><span class="sxs-lookup"><span data-stu-id="b09a8-109">You can also use the techniques described in this section to transform semi-structured text data to XML.</span></span> <span data-ttu-id="b09a8-110">Per ulteriori informazioni, vedere [procedura: generare XML da file CSV](how-to-generate-xml-from-csv-files.md).</span><span class="sxs-lookup"><span data-stu-id="b09a8-110">For more information, see [How to: Generate XML from CSV Files](how-to-generate-xml-from-csv-files.md).</span></span>  
  
 <span data-ttu-id="b09a8-111">Negli esempi inclusi in questa sezione rientrano in due categorie:</span><span class="sxs-lookup"><span data-stu-id="b09a8-111">The examples in this section fall into two categories:</span></span>  
  
## <a name="querying-a-block-of-text"></a><span data-ttu-id="b09a8-112">Esecuzione di query su un blocco di testo</span><span class="sxs-lookup"><span data-stu-id="b09a8-112">Querying a Block of Text</span></span>  
 <span data-ttu-id="b09a8-113">È possibile eseguire una query, analizzare e modificare i blocchi di testo suddividendoli in una matrice queryable di stringhe più piccole utilizzando il <xref:System.String.Split%2A>metodo o <xref:System.Text.RegularExpressions.Regex.Split%2A>(metodo).</xref:System.Text.RegularExpressions.Regex.Split%2A> </xref:System.String.Split%2A></span><span class="sxs-lookup"><span data-stu-id="b09a8-113">You can query, analyze, and modify text blocks by splitting them into a queryable array of smaller strings by using the <xref:System.String.Split%2A> method or the <xref:System.Text.RegularExpressions.Regex.Split%2A> method.</span></span> <span data-ttu-id="b09a8-114">È possibile suddividere il testo di origine in parole, frasi, paragrafi, pagine o altri criteri e quindi eseguire ulteriori suddivisioni se sono richiesti nella query.</span><span class="sxs-lookup"><span data-stu-id="b09a8-114">You can split the source text into words, sentences, paragraphs, pages, or any other criteria, and then perform additional splits if they are required in your query.</span></span>  
  
 [<span data-ttu-id="b09a8-115">Procedura: contare le occorrenze di una parola in una stringa (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b09a8-115">How to: Count Occurrences of a Word in a String (LINQ) (Visual Basic)</span></span>](how-to-count-occurrences-of-a-word-in-a-string-linq.md)  
 <span data-ttu-id="b09a8-116">Viene illustrato come utilizzare LINQ per eseguire una query semplice sul testo.</span><span class="sxs-lookup"><span data-stu-id="b09a8-116">Shows how to use LINQ for simple querying over text.</span></span>  
  
 [<span data-ttu-id="b09a8-117">Procedura: eseguire una Query per trovare frasi che contengono un Set specificato di parole (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b09a8-117">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)</span></span>](how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)

 <span data-ttu-id="b09a8-118">Viene illustrato come suddividere i file di testo su limiti arbitrari e come eseguire query su ciascuna parte.</span><span class="sxs-lookup"><span data-stu-id="b09a8-118">Shows how to split text files on arbitrary boundaries and how to perform queries against each part.</span></span>  
  
 [<span data-ttu-id="b09a8-119">Procedura: eseguire una Query per i caratteri in una stringa (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b09a8-119">How to: Query for Characters in a String (LINQ) (Visual Basic)</span></span>](how-to-query-for-characters-in-a-string-linq.md)  
 <span data-ttu-id="b09a8-120">Viene illustrato che una stringa è un tipo queryable.</span><span class="sxs-lookup"><span data-stu-id="b09a8-120">Demonstrates that a string is a queryable type.</span></span>  
  
 [<span data-ttu-id="b09a8-121">Procedura: combinare query LINQ con espressioni regolari (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b09a8-121">How to: Combine LINQ Queries with Regular Expressions (Visual Basic)</span></span>](how-to-combine-linq-queries-with-regular-expressions.md)  
 <span data-ttu-id="b09a8-122">Viene illustrato come utilizzare espressioni regolari nelle query LINQ per complesso criteri di ricerca nei risultati della query filtrati.</span><span class="sxs-lookup"><span data-stu-id="b09a8-122">Shows how to use regular expressions in LINQ queries for complex pattern matching on filtered query results.</span></span>  
  
## <a name="querying-semi-structured-data-in-text-format"></a><span data-ttu-id="b09a8-123">Esecuzione di query su dati semistrutturati in formato testo</span><span class="sxs-lookup"><span data-stu-id="b09a8-123">Querying Semi-Structured Data in Text Format</span></span>  
 <span data-ttu-id="b09a8-124">Molti tipi diversi di file di testo sono costituiti da una serie di linee, spesso con formattazione simile, ad esempio file delimitato da tabulazione o virgole o righe di lunghezza fissa.</span><span class="sxs-lookup"><span data-stu-id="b09a8-124">Many different types of text files consist of a series of lines, often with similar formatting, such as tab- or comma-delimited files or fixed-length lines.</span></span> <span data-ttu-id="b09a8-125">Dopo aver letto un file di testo in memoria, è possibile utilizzare LINQ per eseguire una query e/o modificare le righe.</span><span class="sxs-lookup"><span data-stu-id="b09a8-125">After you read such a text file into memory, you can use LINQ to query and/or modify the lines.</span></span> <span data-ttu-id="b09a8-126">Le query LINQ semplificano anche la combinazione dei dati da più origini.</span><span class="sxs-lookup"><span data-stu-id="b09a8-126">LINQ queries also simplify the task of combining data from multiple sources.</span></span>  
  
 [<span data-ttu-id="b09a8-127">Procedura: trovare la differenza dei Set tra due elenchi (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b09a8-127">How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)</span></span>](how-to-find-the-set-difference-between-two-lists-linq.md)  
 <span data-ttu-id="b09a8-128">Viene illustrato come trovare tutte le stringhe che sono presenti in un elenco ma non l'altro.</span><span class="sxs-lookup"><span data-stu-id="b09a8-128">Shows how to find all the strings that are present in one list but not the other.</span></span>  
  
 [<span data-ttu-id="b09a8-129">Procedura: ordinare o filtrare i dati di testo da qualsiasi parola o campo (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b09a8-129">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)  
 <span data-ttu-id="b09a8-130">Viene illustrato come ordinare le righe di testo in base a qualsiasi parola o campo.</span><span class="sxs-lookup"><span data-stu-id="b09a8-130">Shows how to sort text lines based on any word or field.</span></span>  
  
 [<span data-ttu-id="b09a8-131">Procedura: riordinare i campi di un File delimitato (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b09a8-131">How to: Reorder the Fields of a Delimited File (LINQ) (Visual Basic)</span></span>](how-to-reorder-the-fields-of-a-delimited-file.md)  
 <span data-ttu-id="b09a8-132">Di seguito viene illustrato come riordinare i campi in una riga in un file con estensione csv.</span><span class="sxs-lookup"><span data-stu-id="b09a8-132">Shows how to reorder fields in a line in a .csv file.</span></span>  
  
 [<span data-ttu-id="b09a8-133">Procedura: combinare e confrontare raccolte di stringhe (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b09a8-133">How to: Combine and Compare String Collections (LINQ) (Visual Basic)</span></span>](how-to-combine-and-compare-string-collections-linq.md)  
 <span data-ttu-id="b09a8-134">Viene illustrato come combinare elenchi di stringhe in vari modi.</span><span class="sxs-lookup"><span data-stu-id="b09a8-134">Shows how to combine string lists in various ways.</span></span>  
  
 [<span data-ttu-id="b09a8-135">Procedura: popolare raccolte di oggetti da più origini (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b09a8-135">How to: Populate Object Collections from Multiple Sources (LINQ) (Visual Basic)</span></span>](how-to-populate-object-collections-from-multiple-sources-linq.md)  
 <span data-ttu-id="b09a8-136">Viene illustrato come creare raccolte di oggetti utilizzando più file di testo come origini dati.</span><span class="sxs-lookup"><span data-stu-id="b09a8-136">Shows how to create object collections by using multiple text files as data sources.</span></span>  
  
 [<span data-ttu-id="b09a8-137">Procedura: unire contenuto da file dissimili (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b09a8-137">How to: Join Content from Dissimilar Files (LINQ) (Visual Basic)</span></span>](how-to-join-content-from-dissimilar-files-linq.md)  
 <span data-ttu-id="b09a8-138">Viene illustrato come combinare le stringhe in due elenchi in un'unica stringa utilizzando una chiave corrispondente.</span><span class="sxs-lookup"><span data-stu-id="b09a8-138">Shows how to combine strings in two lists into a single string by using a matching key.</span></span>  
  
 [<span data-ttu-id="b09a8-139">Procedura: suddividere un File in molti file utilizzando i gruppi (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b09a8-139">How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)</span></span>](how-to-split-a-file-into-many-files-by-using-groups-linq.md)  
 <span data-ttu-id="b09a8-140">Di seguito viene illustrato come creare nuovi file utilizzando un singolo file come origine dati.</span><span class="sxs-lookup"><span data-stu-id="b09a8-140">Shows how to create new files by using a single file as a data source.</span></span>  
  
 [<span data-ttu-id="b09a8-141">Procedura: calcolare i valori di colonna in un File di testo CSV (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b09a8-141">How to: Compute Column Values in a CSV Text File (LINQ) (Visual Basic)</span></span>](how-to-compute-column-values-in-a-csv-text-file-linq.md)  
 <span data-ttu-id="b09a8-142">Viene illustrato come eseguire calcoli matematici sui dati di testo in file con estensione csv.</span><span class="sxs-lookup"><span data-stu-id="b09a8-142">Shows how to perform mathematical computations on text data in .csv files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b09a8-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b09a8-143">See Also</span></span>  
 <span data-ttu-id="b09a8-144">[Language-Integrated Query (LINQ) (Visual Basic)](index.md) </span><span class="sxs-lookup"><span data-stu-id="b09a8-144">[Language-Integrated Query (LINQ) (Visual Basic)](index.md) </span></span>  
<span data-ttu-id="b09a8-145"> [Procedura: generare XML da file CSV](how-to-generate-xml-from-csv-files.md)</span><span class="sxs-lookup"><span data-stu-id="b09a8-145"> [How to: Generate XML from CSV Files](how-to-generate-xml-from-csv-files.md)</span></span>

