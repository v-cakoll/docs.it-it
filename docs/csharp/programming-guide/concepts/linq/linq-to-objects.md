---
title: LINQ to Objects (C#)
description: Informazioni sulle LINQ to Objects in C#, che usa query LINQ con qualsiasi raccolta IEnumerable o IEnumerable <T> senza un'API o un provider LINQ intermedio.
ms.date: 07/20/2015
ms.assetid: c5c2c178-3529-4f6c-b3df-2d5267af7f22
ms.openlocfilehash: 7b67690ee13f207441bc94155acd91047b63b3df
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165548"
---
# <a name="linq-to-objects-c"></a><span data-ttu-id="5df06-103">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="5df06-103">LINQ to Objects (C#)</span></span>

<span data-ttu-id="5df06-104">Il termine "LINQ to Objects" si riferisce all'utilizzo diretto di query LINQ con qualsiasi raccolta <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601>, senza l'utilizzo di un'API o un provider LINQ intermedio, come per [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) o [LINQ to XML](./linq-to-xml-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5df06-104">The term "LINQ to Objects" refers to the use of LINQ queries with any <xref:System.Collections.IEnumerable> or <xref:System.Collections.Generic.IEnumerable%601> collection directly, without the use of an intermediate LINQ provider or API such as [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) or [LINQ to XML](./linq-to-xml-overview.md).</span></span> <span data-ttu-id="5df06-105">È possibile usare LINQ per eseguire una query su qualsiasi raccolta enumerabile, ad esempio <xref:System.Collections.Generic.List%601>, <xref:System.Array> o <xref:System.Collections.Generic.Dictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="5df06-105">You can use LINQ to query any enumerable collections such as <xref:System.Collections.Generic.List%601>, <xref:System.Array>, or <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="5df06-106">La raccolta può essere definita dall'utente o può essere restituita da un'API .NET.</span><span class="sxs-lookup"><span data-stu-id="5df06-106">The collection may be user-defined or may be returned by a .NET API.</span></span>  
  
 <span data-ttu-id="5df06-107">Come concetto di base, LINQ to Objects rappresenta un nuovo approccio alle raccolte.</span><span class="sxs-lookup"><span data-stu-id="5df06-107">In a basic sense, LINQ to Objects represents a new approach to collections.</span></span> <span data-ttu-id="5df06-108">In passato, era necessario scrivere cicli `foreach` complessi che specificavano come recuperare i dati da una raccolta.</span><span class="sxs-lookup"><span data-stu-id="5df06-108">In the old way, you had to write complex `foreach` loops that specified how to retrieve data from a collection.</span></span> <span data-ttu-id="5df06-109">Con l'approccio LINQ, è possibile scrivere il codice dichiarativo che descrive i dati da recuperare.</span><span class="sxs-lookup"><span data-stu-id="5df06-109">In the LINQ approach, you write declarative code that describes what you want to retrieve.</span></span>  
  
 <span data-ttu-id="5df06-110">Le query LINQ offrono anche tre vantaggi principali rispetto ai cicli `foreach` tradizionali:</span><span class="sxs-lookup"><span data-stu-id="5df06-110">In addition, LINQ queries offer three main advantages over traditional `foreach` loops:</span></span>  
  
- <span data-ttu-id="5df06-111">Sono più brevi e leggibili, soprattutto quando si filtrano più condizioni.</span><span class="sxs-lookup"><span data-stu-id="5df06-111">They are more concise and readable, especially when filtering multiple conditions.</span></span>  
  
- <span data-ttu-id="5df06-112">Forniscono funzioni potenti di filtro, ordinamento e raggruppamento con un codice dell'applicazione minimo.</span><span class="sxs-lookup"><span data-stu-id="5df06-112">They provide powerful filtering, ordering, and grouping capabilities with a minimum of application code.</span></span>  
  
- <span data-ttu-id="5df06-113">Possono essere trasferiti in altre origini dati con modifiche minime o nulle.</span><span class="sxs-lookup"><span data-stu-id="5df06-113">They can be ported to other data sources with little or no modification.</span></span>  
  
 <span data-ttu-id="5df06-114">In generale, più è complessa l'operazione che si vuole eseguire sui dati, maggiore sarà il vantaggio che si realizzerà usando LINQ anziché le tecniche di iterazione tradizionali.</span><span class="sxs-lookup"><span data-stu-id="5df06-114">In general, the more complex the operation you want to perform on the data, the more benefit you'll realize by using LINQ instead of traditional iteration techniques.</span></span>  
  
 <span data-ttu-id="5df06-115">Lo scopo di questa sezione è illustrare l'approccio LINQ con alcuni esempi specificamente selezionati.</span><span class="sxs-lookup"><span data-stu-id="5df06-115">The purpose of this section is to demonstrate the LINQ approach with some select examples.</span></span> <span data-ttu-id="5df06-116">Non è destinato a essere esaustivo.</span><span class="sxs-lookup"><span data-stu-id="5df06-116">It's not intended to be exhaustive.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5df06-117">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="5df06-117">In This Section</span></span>  
 [<span data-ttu-id="5df06-118">LINQ e stringhe (C#)</span><span class="sxs-lookup"><span data-stu-id="5df06-118">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)  
 <span data-ttu-id="5df06-119">Viene illustrato come usare LINQ per eseguire query e trasformare stringhe e raccolte di stringhe.</span><span class="sxs-lookup"><span data-stu-id="5df06-119">Explains how LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="5df06-120">Include anche collegamenti ad articoli che illustrano questi principi.</span><span class="sxs-lookup"><span data-stu-id="5df06-120">Also includes links to articles that demonstrate these principles.</span></span>  
  
 [<span data-ttu-id="5df06-121">LINQ e reflection (C#)</span><span class="sxs-lookup"><span data-stu-id="5df06-121">LINQ and Reflection (C#)</span></span>](how-to-query-an-assembly-s-metadata-with-reflection-linq.md)  
 <span data-ttu-id="5df06-122">Collegamenti a un esempio che illustra l'uso di reflection in LINQ.</span><span class="sxs-lookup"><span data-stu-id="5df06-122">Links to a sample that demonstrates how LINQ uses reflection.</span></span>  
  
 [<span data-ttu-id="5df06-123">Directory di file e LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="5df06-123">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)  
 <span data-ttu-id="5df06-124">Viene illustrato come usare LINQ per interagire con i file system.</span><span class="sxs-lookup"><span data-stu-id="5df06-124">Explains how LINQ can be used to interact with file systems.</span></span> <span data-ttu-id="5df06-125">Sono inoltre inclusi collegamenti ad articoli in cui vengono illustrati questi concetti.</span><span class="sxs-lookup"><span data-stu-id="5df06-125">Also includes links to articles that demonstrate these concepts.</span></span>  
  
 [<span data-ttu-id="5df06-126">Come eseguire una query su un ArrayList con LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="5df06-126">How to query an ArrayList with LINQ (C#)</span></span>](./how-to-query-an-arraylist-with-linq.md)  
 <span data-ttu-id="5df06-127">Viene illustrato come eseguire una query su un oggetto ArrayList in C#.</span><span class="sxs-lookup"><span data-stu-id="5df06-127">Demonstrates how to query an ArrayList in C#.</span></span>  
  
 [<span data-ttu-id="5df06-128">Come aggiungere metodi personalizzati per le query LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="5df06-128">How to add custom methods for LINQ queries (C#)</span></span>](./how-to-add-custom-methods-for-linq-queries.md)  
 <span data-ttu-id="5df06-129">Spiega come estendere il set di metodi utilizzabili per le query LINQ aggiungendo metodi di estensione all'interfaccia <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="5df06-129">Explains how to extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>  
  
 [<span data-ttu-id="5df06-130">LINQ (Language-Integrated Query) (C#)</span><span class="sxs-lookup"><span data-stu-id="5df06-130">Language-Integrated Query (LINQ) (C#)</span></span>](./index.md)  
 <span data-ttu-id="5df06-131">Vengono forniti collegamenti ad articoli che illustrano LINQ e forniscono esempi di codice che eseguono query.</span><span class="sxs-lookup"><span data-stu-id="5df06-131">Provides links to articles that explain LINQ and provide examples of code that perform queries.</span></span>
