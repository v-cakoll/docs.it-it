---
title: LINQ to Objects (C#)
ms.date: 07/20/2015
ms.assetid: c5c2c178-3529-4f6c-b3df-2d5267af7f22
ms.openlocfilehash: c488e49283f3e30ea729adf111fd9ca297039838
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241565"
---
# <a name="linq-to-objects-c"></a><span data-ttu-id="ae95f-102">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="ae95f-102">LINQ to Objects (C#)</span></span>
<span data-ttu-id="ae95f-103">Il termine "LINQ to Objects" si riferisce all'utilizzo diretto di query LINQ con qualsiasi raccolta <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601>, senza l'utilizzo di un'API o un provider LINQ intermedio, come per [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) o [LINQ to XML](./linq-to-xml-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ae95f-103">The term "LINQ to Objects" refers to the use of LINQ queries with any <xref:System.Collections.IEnumerable> or <xref:System.Collections.Generic.IEnumerable%601> collection directly, without the use of an intermediate LINQ provider or API such as [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) or [LINQ to XML](./linq-to-xml-overview.md).</span></span> <span data-ttu-id="ae95f-104">È possibile usare LINQ per eseguire una query su qualsiasi raccolta enumerabile, ad esempio <xref:System.Collections.Generic.List%601>, <xref:System.Array> o <xref:System.Collections.Generic.Dictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="ae95f-104">You can use LINQ to query any enumerable collections such as <xref:System.Collections.Generic.List%601>, <xref:System.Array>, or <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="ae95f-105">La raccolta può essere definita dall'utente o può essere restituita da un'API .NET.</span><span class="sxs-lookup"><span data-stu-id="ae95f-105">The collection may be user-defined or may be returned by a .NET API.</span></span>  
  
 <span data-ttu-id="ae95f-106">Come concetto di base, LINQ to Objects rappresenta un nuovo approccio alle raccolte.</span><span class="sxs-lookup"><span data-stu-id="ae95f-106">In a basic sense, LINQ to Objects represents a new approach to collections.</span></span> <span data-ttu-id="ae95f-107">In passato, era necessario scrivere cicli `foreach` complessi che specificavano come recuperare i dati da una raccolta.</span><span class="sxs-lookup"><span data-stu-id="ae95f-107">In the old way, you had to write complex `foreach` loops that specified how to retrieve data from a collection.</span></span> <span data-ttu-id="ae95f-108">Con l'approccio LINQ, è possibile scrivere il codice dichiarativo che descrive i dati da recuperare.</span><span class="sxs-lookup"><span data-stu-id="ae95f-108">In the LINQ approach, you write declarative code that describes what you want to retrieve.</span></span>  
  
 <span data-ttu-id="ae95f-109">Le query LINQ offrono anche tre vantaggi principali rispetto ai cicli `foreach` tradizionali:</span><span class="sxs-lookup"><span data-stu-id="ae95f-109">In addition, LINQ queries offer three main advantages over traditional `foreach` loops:</span></span>  
  
1. <span data-ttu-id="ae95f-110">Sono più brevi e leggibili, soprattutto quando si filtrano più condizioni.</span><span class="sxs-lookup"><span data-stu-id="ae95f-110">They are more concise and readable, especially when filtering multiple conditions.</span></span>  
  
2. <span data-ttu-id="ae95f-111">Forniscono funzioni potenti di filtro, ordinamento e raggruppamento con un codice dell'applicazione minimo.</span><span class="sxs-lookup"><span data-stu-id="ae95f-111">They provide powerful filtering, ordering, and grouping capabilities with a minimum of application code.</span></span>  
  
3. <span data-ttu-id="ae95f-112">Possono essere trasferiti in altre origini dati con modifiche minime o nulle.</span><span class="sxs-lookup"><span data-stu-id="ae95f-112">They can be ported to other data sources with little or no modification.</span></span>  
  
 <span data-ttu-id="ae95f-113">In generale, più è complessa l'operazione da eseguire sui dati, maggiore sarà il vantaggio che si potrà trarre dall'uso di LINQ rispetto alle tecniche di iterazione tradizionali.</span><span class="sxs-lookup"><span data-stu-id="ae95f-113">In general, the more complex the operation you want to perform on the data, the more benefit you will realize by using LINQ instead of traditional iteration techniques.</span></span>  
  
 <span data-ttu-id="ae95f-114">Lo scopo di questa sezione è illustrare l'approccio LINQ con alcuni esempi specificamente selezionati.</span><span class="sxs-lookup"><span data-stu-id="ae95f-114">The purpose of this section is to demonstrate the LINQ approach with some select examples.</span></span> <span data-ttu-id="ae95f-115">Tali informazioni non devono essere ritenute esaustive.</span><span class="sxs-lookup"><span data-stu-id="ae95f-115">It is not intended to be exhaustive.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ae95f-116">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="ae95f-116">In This Section</span></span>  
 [<span data-ttu-id="ae95f-117">LINQ e stringhe (C#)</span><span class="sxs-lookup"><span data-stu-id="ae95f-117">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)  
 <span data-ttu-id="ae95f-118">Viene illustrato come usare LINQ per eseguire query e trasformare stringhe e raccolte di stringhe.</span><span class="sxs-lookup"><span data-stu-id="ae95f-118">Explains how LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="ae95f-119">Include anche collegamenti ad argomenti che illustrano questi principi.</span><span class="sxs-lookup"><span data-stu-id="ae95f-119">Also includes links to topics that demonstrate these principles.</span></span>  
  
 [<span data-ttu-id="ae95f-120">LINQ e reflection (C#)</span><span class="sxs-lookup"><span data-stu-id="ae95f-120">LINQ and Reflection (C#)</span></span>](how-to-query-an-assembly-s-metadata-with-reflection-linq.md)  
 <span data-ttu-id="ae95f-121">Collegamenti a un esempio che illustra l'uso di reflection in LINQ.</span><span class="sxs-lookup"><span data-stu-id="ae95f-121">Links to a sample that demonstrates how LINQ uses reflection.</span></span>  
  
 [<span data-ttu-id="ae95f-122">Directory di file e LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="ae95f-122">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)  
 <span data-ttu-id="ae95f-123">Viene illustrato come usare LINQ per interagire con i file system.</span><span class="sxs-lookup"><span data-stu-id="ae95f-123">Explains how LINQ can be used to interact with file systems.</span></span> <span data-ttu-id="ae95f-124">Include anche collegamenti ad argomenti che illustrano questi concetti.</span><span class="sxs-lookup"><span data-stu-id="ae95f-124">Also includes links to topics that demonstrate these concepts.</span></span>  
  
 [<span data-ttu-id="ae95f-125">Come eseguire una query su un ArrayList con LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="ae95f-125">How to query an ArrayList with LINQ (C#)</span></span>](./how-to-query-an-arraylist-with-linq.md)  
 <span data-ttu-id="ae95f-126">Viene illustrato come eseguire una query su un oggetto ArrayList in C#.</span><span class="sxs-lookup"><span data-stu-id="ae95f-126">Demonstrates how to query an ArrayList in C#.</span></span>  
  
 [<span data-ttu-id="ae95f-127">Come aggiungere metodi personalizzati per le query LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="ae95f-127">How to add custom methods for LINQ queries (C#)</span></span>](./how-to-add-custom-methods-for-linq-queries.md)  
 <span data-ttu-id="ae95f-128">Spiega come estendere il set di metodi utilizzabili per le query LINQ aggiungendo metodi di estensione all'interfaccia <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="ae95f-128">Explains how to extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>  
  
 [<span data-ttu-id="ae95f-129">LINQ (Language-Integrated Query) (C#)</span><span class="sxs-lookup"><span data-stu-id="ae95f-129">Language-Integrated Query (LINQ) (C#)</span></span>](./index.md)  
 <span data-ttu-id="ae95f-130">Vengono specificati collegamenti ad argomenti che descrivono LINQ e offrono esempi di codice per l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="ae95f-130">Provides links to topics that explain LINQ and provide examples of code that perform queries.</span></span>
