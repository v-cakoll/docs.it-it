---
title: LINQ e stringhe (C#)
description: LINQ può eseguire query e trasformare stringhe e raccolte di stringhe. È possibile combinare query LINQ con funzioni stringa C# ed espressioni regolari.
ms.date: 07/20/2015
ms.assetid: dbe2d657-b3f3-487e-b645-21fb2d71cd7b
ms.openlocfilehash: c515a0c56ad6473f93c6339540e4ed0245bb5bd2
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165610"
---
# <a name="linq-and-strings-c"></a><span data-ttu-id="913ae-104">LINQ e stringhe (C#)</span><span class="sxs-lookup"><span data-stu-id="913ae-104">LINQ and strings (C#)</span></span>

<span data-ttu-id="913ae-105">È possibile usare LINQ per eseguire query e trasformare stringhe e raccolte di stringhe.</span><span class="sxs-lookup"><span data-stu-id="913ae-105">LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="913ae-106">LINQ può essere particolarmente utile con i dati semistrutturati nei file di testo.</span><span class="sxs-lookup"><span data-stu-id="913ae-106">It can be especially useful with semi-structured data in text files.</span></span> <span data-ttu-id="913ae-107">Le query LINQ possono essere usate in associazione a funzioni per valori stringa tradizionali ed espressioni regolari.</span><span class="sxs-lookup"><span data-stu-id="913ae-107">LINQ queries can be combined with traditional string functions and regular expressions.</span></span> <span data-ttu-id="913ae-108">Ad esempio, è possibile usare il metodo <xref:System.String.Split%2A?displayProperty=nameWithType> o <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> per creare una matrice di stringhe in cui sarà possibile eseguire query o apportare modifiche usando LINQ.</span><span class="sxs-lookup"><span data-stu-id="913ae-108">For example, you can use the <xref:System.String.Split%2A?displayProperty=nameWithType> or <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> method to create an array of strings that you can then query or modify by using LINQ.</span></span> <span data-ttu-id="913ae-109">È possibile usare il metodo <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> nella clausola `where` di una query LINQ.</span><span class="sxs-lookup"><span data-stu-id="913ae-109">You can use the <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> method in the `where` clause of a LINQ query.</span></span> <span data-ttu-id="913ae-110">È anche possibile usare LINQ per eseguire query o modificare i risultati <xref:System.Text.RegularExpressions.MatchCollection> restituiti da un'espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="913ae-110">And you can use LINQ to query or modify the <xref:System.Text.RegularExpressions.MatchCollection> results returned by a regular expression.</span></span>

<span data-ttu-id="913ae-111">È anche possibile usare le tecniche descritte in questa sezione per trasformare dati di testo semistrutturati in XML.</span><span class="sxs-lookup"><span data-stu-id="913ae-111">You can also use the techniques described in this section to transform semi-structured text data to XML.</span></span> <span data-ttu-id="913ae-112">Per ulteriori informazioni, vedere [come generare XML da file CSV](how-to-generate-xml-from-csv-files.md).</span><span class="sxs-lookup"><span data-stu-id="913ae-112">For more information, see [How to generate XML from CSV files](how-to-generate-xml-from-csv-files.md).</span></span>

<span data-ttu-id="913ae-113">Gli esempi di questa sezione sono suddivisi in due categorie:</span><span class="sxs-lookup"><span data-stu-id="913ae-113">The examples in this section fall into two categories:</span></span>

## <a name="querying-a-block-of-text"></a><span data-ttu-id="913ae-114">Esecuzione di query in un blocco di testo</span><span class="sxs-lookup"><span data-stu-id="913ae-114">Querying a block of text</span></span>

<span data-ttu-id="913ae-115">È possibile eseguire query, analizzare e modificare blocchi di testo suddividendoli in una matrice di stringhe più piccole sottoponibile a query usando il metodo <xref:System.String.Split%2A?displayProperty=nameWithType> o <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="913ae-115">You can query, analyze, and modify text blocks by splitting them into a queryable array of smaller strings by using the <xref:System.String.Split%2A?displayProperty=nameWithType> method or the <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="913ae-116">È possibile suddividere il testo di origine in parole, frasi, paragrafi, pagine o altri criteri e quindi eseguire altre suddivisioni se richieste nella query.</span><span class="sxs-lookup"><span data-stu-id="913ae-116">You can split the source text into words, sentences, paragraphs, pages, or any other criteria, and then perform additional splits if they are required in your query.</span></span>

- [<span data-ttu-id="913ae-117">Come contare le occorrenze di una parola in una stringa (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="913ae-117">How to count occurrences of a word in a string (LINQ) (C#)</span></span>](how-to-count-occurrences-of-a-word-in-a-string-linq.md)  
  <span data-ttu-id="913ae-118">Descrive come usare LINQ per eseguire query semplici nel testo.</span><span class="sxs-lookup"><span data-stu-id="913ae-118">Shows how to use LINQ for simple querying over text.</span></span>

- [<span data-ttu-id="913ae-119">Come eseguire una query per trovare frasi che contengono un set specificato di parole (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="913ae-119">How to query for sentences that contain a specified set of words (LINQ) (C#)</span></span>](how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)

  <span data-ttu-id="913ae-120">Descrive come suddividere file di testo su limiti arbitrari e come eseguire query in ogni parte.</span><span class="sxs-lookup"><span data-stu-id="913ae-120">Shows how to split text files on arbitrary boundaries and how to perform queries against each part.</span></span>

- [<span data-ttu-id="913ae-121">Come eseguire una query per i caratteri in una stringa (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="913ae-121">How to query for characters in a string (LINQ) (C#)</span></span>](how-to-query-for-characters-in-a-string-linq.md)

  <span data-ttu-id="913ae-122">Dimostra che una stringa è un tipo sottoponibile a query.</span><span class="sxs-lookup"><span data-stu-id="913ae-122">Demonstrates that a string is a queryable type.</span></span>

- [<span data-ttu-id="913ae-123">Come combinare query LINQ con espressioni regolari (C#)</span><span class="sxs-lookup"><span data-stu-id="913ae-123">How to combine LINQ queries with regular expressions (C#)</span></span>](how-to-combine-linq-queries-with-regular-expressions.md)

  <span data-ttu-id="913ae-124">Descrive come usare le espressioni regolari nelle query LINQ per un modello complesso corrispondente ai risultati della query filtrati.</span><span class="sxs-lookup"><span data-stu-id="913ae-124">Shows how to use regular expressions in LINQ queries for complex pattern matching on filtered query results.</span></span>

## <a name="querying-semi-structured-data-in-text-format"></a><span data-ttu-id="913ae-125">Esecuzione di query di dati semistrutturati in formato testo</span><span class="sxs-lookup"><span data-stu-id="913ae-125">Querying semi-structured data in text format</span></span>

<span data-ttu-id="913ae-126">Numerosi tipi di file di testo sono costituiti da una serie di righe, spesso con formattazione simile, ad esempio file delimitati da tabulazione o virgola o righe a lunghezza fissa.</span><span class="sxs-lookup"><span data-stu-id="913ae-126">Many different types of text files consist of a series of lines, often with similar formatting, such as tab- or comma-delimited files or fixed-length lines.</span></span> <span data-ttu-id="913ae-127">Dopo la lettura del file di testo in memoria, è possibile usare LINQ per eseguire query e/o modificare le righe.</span><span class="sxs-lookup"><span data-stu-id="913ae-127">After you read such a text file into memory, you can use LINQ to query and/or modify the lines.</span></span> <span data-ttu-id="913ae-128">Le query LINQ semplificano anche la combinazione di dati di più origini.</span><span class="sxs-lookup"><span data-stu-id="913ae-128">LINQ queries also simplify the task of combining data from multiple sources.</span></span>

- [<span data-ttu-id="913ae-129">Come trovare la differenza dei set tra due elenchi (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="913ae-129">How to find the set difference between two lists (LINQ) (C#)</span></span>](how-to-find-the-set-difference-between-two-lists-linq.md)

  <span data-ttu-id="913ae-130">Descrive come trovare tutte le stringhe presenti in un elenco ma non in un altro elenco.</span><span class="sxs-lookup"><span data-stu-id="913ae-130">Shows how to find all the strings that are present in one list but not the other.</span></span>

- [<span data-ttu-id="913ae-131">Come ordinare o filtrare i dati di testo in base a qualsiasi parola o campo (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="913ae-131">How to sort or filter text data by any word or field (LINQ) (C#)</span></span>](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)

  <span data-ttu-id="913ae-132">Descrive come ordinare le righe di testo in base a una parola o un campo.</span><span class="sxs-lookup"><span data-stu-id="913ae-132">Shows how to sort text lines based on any word or field.</span></span>

- [<span data-ttu-id="913ae-133">Come riordinare i campi di un file delimitato (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="913ae-133">How to reorder the fields of a delimited file (LINQ) (C#)</span></span>](how-to-reorder-the-fields-of-a-delimited-file-linq.md)

  <span data-ttu-id="913ae-134">Descrive come riordinare i campi in una riga in un file con estensione csv.</span><span class="sxs-lookup"><span data-stu-id="913ae-134">Shows how to reorder fields in a line in a .csv file.</span></span>

- [<span data-ttu-id="913ae-135">Come combinare e confrontare raccolte di stringhe (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="913ae-135">How to combine and compare string collections (LINQ) (C#)</span></span>](how-to-combine-and-compare-string-collections-linq.md)

  <span data-ttu-id="913ae-136">Descrive come combinare elenchi di stringhe in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="913ae-136">Shows how to combine string lists in various ways.</span></span>

- [<span data-ttu-id="913ae-137">Come popolare le raccolte di oggetti da più origini (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="913ae-137">How to populate object collections from multiple sources (LINQ) (C#)</span></span>](how-to-populate-object-collections-from-multiple-sources-linq.md)

  <span data-ttu-id="913ae-138">Descrive come creare raccolte di oggetti usando più file di testo come origini dati.</span><span class="sxs-lookup"><span data-stu-id="913ae-138">Shows how to create object collections by using multiple text files as data sources.</span></span>

- [<span data-ttu-id="913ae-139">Come unire il contenuto da file non analoghi (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="913ae-139">How to join content from dissimilar files (LINQ) (C#)</span></span>](how-to-join-content-from-dissimilar-files-linq.md)
  
  <span data-ttu-id="913ae-140">Descrive come combinare le stringhe in due elenchi in un'unica stringa usando una chiave corrispondente.</span><span class="sxs-lookup"><span data-stu-id="913ae-140">Shows how to combine strings in two lists into a single string by using a matching key.</span></span>

- [<span data-ttu-id="913ae-141">Come suddividere un file in molti file usando i gruppi (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="913ae-141">How to split a file into many files by using groups (LINQ) (C#)</span></span>](how-to-split-a-file-into-many-files-by-using-groups-linq.md)
  
  <span data-ttu-id="913ae-142">Descrive come creare file nuovi usando un singolo file come origine dati.</span><span class="sxs-lookup"><span data-stu-id="913ae-142">Shows how to create new files by using a single file as a data source.</span></span>

- [<span data-ttu-id="913ae-143">Come calcolare i valori di colonna in un file di testo CSV (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="913ae-143">How to compute column values in a CSV text file (LINQ) (C#)</span></span>](how-to-compute-column-values-in-a-csv-text-file-linq.md)
  
  <span data-ttu-id="913ae-144">Descrive come eseguire calcoli matematici in dati di testo in file con estensione csv.</span><span class="sxs-lookup"><span data-stu-id="913ae-144">Shows how to perform mathematical computations on text data in .csv files.</span></span>

## <a name="see-also"></a><span data-ttu-id="913ae-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="913ae-145">See also</span></span>

- [<span data-ttu-id="913ae-146">LINQ (Language-Integrated Query) (C#)</span><span class="sxs-lookup"><span data-stu-id="913ae-146">Language-Integrated Query (LINQ) (C#)</span></span>](index.md)
- [<span data-ttu-id="913ae-147">Come generare XML da file CSV</span><span class="sxs-lookup"><span data-stu-id="913ae-147">How to generate XML from CSV files</span></span>](how-to-generate-xml-from-csv-files.md)
