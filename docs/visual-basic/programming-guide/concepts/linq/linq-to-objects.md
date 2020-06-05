---
title: LINQ to Objects
ms.date: 07/20/2015
ms.assetid: dd4c30bc-1c9b-4781-a482-b5eada38deb2
ms.openlocfilehash: 1dca449f12c312fd395be56ebcb426c3a63b64d0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84369063"
---
# <a name="linq-to-objects-visual-basic"></a><span data-ttu-id="5576e-102">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5576e-102">LINQ to Objects (Visual Basic)</span></span>
<span data-ttu-id="5576e-103">Il termine "LINQ to Objects" si riferisce all'utilizzo diretto di query LINQ con qualsiasi raccolta <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601>, senza l'utilizzo di un'API o un provider LINQ intermedio, come per [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) o [LINQ to XML](linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="5576e-103">The term "LINQ to Objects" refers to the use of LINQ queries with any <xref:System.Collections.IEnumerable> or <xref:System.Collections.Generic.IEnumerable%601> collection directly, without the use of an intermediate LINQ provider or API such as [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) or [LINQ to XML](linq-to-xml.md).</span></span> <span data-ttu-id="5576e-104">È possibile usare LINQ per eseguire una query su qualsiasi raccolta enumerabile, ad esempio <xref:System.Collections.Generic.List%601>, <xref:System.Array> o <xref:System.Collections.Generic.Dictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="5576e-104">You can use LINQ to query any enumerable collections such as <xref:System.Collections.Generic.List%601>, <xref:System.Array>, or <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="5576e-105">La raccolta può essere definita dall'utente o restituita da un'API di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5576e-105">The collection may be user-defined or may be returned by a .NET Framework API.</span></span>  
  
 <span data-ttu-id="5576e-106">Come concetto di base, LINQ to Objects rappresenta un nuovo approccio alle raccolte.</span><span class="sxs-lookup"><span data-stu-id="5576e-106">In a basic sense, LINQ to Objects represents a new approach to collections.</span></span> <span data-ttu-id="5576e-107">In passato, era necessario scrivere cicli `For Each` complessi che specificavano come recuperare i dati da una raccolta.</span><span class="sxs-lookup"><span data-stu-id="5576e-107">In the old way, you had to write complex `For Each` loops that specified how to retrieve data from a collection.</span></span> <span data-ttu-id="5576e-108">Con l'approccio LINQ, è possibile scrivere il codice dichiarativo che descrive i dati da recuperare.</span><span class="sxs-lookup"><span data-stu-id="5576e-108">In the LINQ approach, you write declarative code that describes what you want to retrieve.</span></span>  
  
 <span data-ttu-id="5576e-109">Le query LINQ offrono anche tre vantaggi principali rispetto ai cicli `For Each` tradizionali:</span><span class="sxs-lookup"><span data-stu-id="5576e-109">In addition, LINQ queries offer three main advantages over traditional `For Each` loops:</span></span>  
  
1. <span data-ttu-id="5576e-110">Sono più brevi e leggibili, soprattutto quando si filtrano più condizioni.</span><span class="sxs-lookup"><span data-stu-id="5576e-110">They are more concise and readable, especially when filtering multiple conditions.</span></span>  
  
2. <span data-ttu-id="5576e-111">Forniscono funzioni potenti di filtro, ordinamento e raggruppamento con un codice dell'applicazione minimo.</span><span class="sxs-lookup"><span data-stu-id="5576e-111">They provide powerful filtering, ordering, and grouping capabilities with a minimum of application code.</span></span>  
  
3. <span data-ttu-id="5576e-112">Possono essere trasferiti in altre origini dati con modifiche minime o nulle.</span><span class="sxs-lookup"><span data-stu-id="5576e-112">They can be ported to other data sources with little or no modification.</span></span>  
  
 <span data-ttu-id="5576e-113">In generale, più è complessa l'operazione da eseguire sui dati, maggiore sarà il vantaggio che si potrà trarre dall'uso di LINQ rispetto alle tecniche di iterazione tradizionali.</span><span class="sxs-lookup"><span data-stu-id="5576e-113">In general, the more complex the operation you want to perform on the data, the more benefit you will realize by using LINQ instead of traditional iteration techniques.</span></span>  
  
 <span data-ttu-id="5576e-114">Lo scopo di questa sezione è illustrare l'approccio LINQ con alcuni esempi specificamente selezionati.</span><span class="sxs-lookup"><span data-stu-id="5576e-114">The purpose of this section is to demonstrate the LINQ approach with some select examples.</span></span> <span data-ttu-id="5576e-115">Tali informazioni non devono essere ritenute esaustive.</span><span class="sxs-lookup"><span data-stu-id="5576e-115">It is not intended to be exhaustive.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5576e-116">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="5576e-116">In This Section</span></span>  
 <span data-ttu-id="5576e-117">[LINQ and Strings (Visual Basic)](linq-and-strings.md) (LINQ e le stringhe (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="5576e-117">[LINQ and Strings (Visual Basic)](linq-and-strings.md)</span></span>  
 <span data-ttu-id="5576e-118">Viene illustrato come usare LINQ per eseguire query e trasformare stringhe e raccolte di stringhe.</span><span class="sxs-lookup"><span data-stu-id="5576e-118">Explains how LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="5576e-119">Include anche collegamenti ad argomenti che illustrano questi principi.</span><span class="sxs-lookup"><span data-stu-id="5576e-119">Also includes links to topics that demonstrate these principles.</span></span>  
  
 [<span data-ttu-id="5576e-120">LINQ e Reflection (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5576e-120">LINQ and Reflection (Visual Basic)</span></span>](linq-and-reflection.md)  
 <span data-ttu-id="5576e-121">Collegamenti a un esempio che illustra l'uso di reflection in LINQ.</span><span class="sxs-lookup"><span data-stu-id="5576e-121">Links to a sample that demonstrates how LINQ uses reflection.</span></span>  
  
 <span data-ttu-id="5576e-122">[LINQ and File Directories (Visual Basic)](linq-and-file-directories.md) (LINQ e directory file (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="5576e-122">[LINQ and File Directories (Visual Basic)](linq-and-file-directories.md)</span></span>  
 <span data-ttu-id="5576e-123">Viene illustrato come usare LINQ per interagire con i file system.</span><span class="sxs-lookup"><span data-stu-id="5576e-123">Explains how LINQ can be used to interact with file systems.</span></span> <span data-ttu-id="5576e-124">Include anche collegamenti ad argomenti che illustrano questi concetti.</span><span class="sxs-lookup"><span data-stu-id="5576e-124">Also includes links to topics that demonstrate these concepts.</span></span>  
  
 [<span data-ttu-id="5576e-125">Procedura: eseguire una query su un ArrayList con LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5576e-125">How to: Query an ArrayList with LINQ (Visual Basic)</span></span>](how-to-query-an-arraylist-with-linq.md)  
 <span data-ttu-id="5576e-126">Viene illustrato come eseguire una query su un oggetto ArrayList in C#.</span><span class="sxs-lookup"><span data-stu-id="5576e-126">Demonstrates how to query an ArrayList in C#.</span></span>  
  
 [<span data-ttu-id="5576e-127">Procedura: aggiungere metodi personalizzati per le query LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5576e-127">How to: Add Custom Methods for LINQ Queries (Visual Basic)</span></span>](how-to-add-custom-methods-for-linq-queries.md)  
 <span data-ttu-id="5576e-128">Spiega come estendere il set di metodi utilizzabili per le query LINQ aggiungendo metodi di estensione all'interfaccia <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="5576e-128">Explains how to extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>  
  
 [<span data-ttu-id="5576e-129">LINQ (Language-Integrated Query) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5576e-129">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](index.md)  
 <span data-ttu-id="5576e-130">Vengono specificati collegamenti ad argomenti che descrivono LINQ e offrono esempi di codice per l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="5576e-130">Provides links to topics that explain LINQ and provide examples of code that perform queries.</span></span>
