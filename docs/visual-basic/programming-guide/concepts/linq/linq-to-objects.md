---
title: LINQ to Objects (Visual Basic) | Documenti di Microsoft
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
ms.assetid: dd4c30bc-1c9b-4781-a482-b5eada38deb2
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
ms.openlocfilehash: 82094ee6232ef5b1884f1b4b15eacb635be758aa
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="linq-to-objects-visual-basic"></a><span data-ttu-id="539bd-102">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="539bd-102">LINQ to Objects (Visual Basic)</span></span>
<span data-ttu-id="539bd-103">Il termine "LINQ agli oggetti" si riferisce all'utilizzo di LINQ una query con qualsiasi <xref:System.Collections.IEnumerable>o <xref:System.Collections.Generic.IEnumerable%601>raccolta direttamente, senza l'utilizzo di un provider LINQ o un'API come intermedio [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) o [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="539bd-103">The term "LINQ to Objects" refers to the use of LINQ queries with any <xref:System.Collections.IEnumerable> or <xref:System.Collections.Generic.IEnumerable%601> collection directly, without the use of an intermediate LINQ provider or API such as [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) or [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</span></span> <span data-ttu-id="539bd-104">È possibile utilizzare LINQ per eseguire query su qualsiasi raccolta enumerabile, ad esempio <xref:System.Collections.Generic.List%601>, <xref:System.Array>, o <xref:System.Collections.Generic.Dictionary%602>.</xref:System.Collections.Generic.Dictionary%602> </xref:System.Array> </xref:System.Collections.Generic.List%601></span><span class="sxs-lookup"><span data-stu-id="539bd-104">You can use LINQ to query any enumerable collections such as <xref:System.Collections.Generic.List%601>, <xref:System.Array>, or <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="539bd-105">La raccolta può essere definita dall'utente o può essere restituita da un'API di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="539bd-105">The collection may be user-defined or may be returned by a .NET Framework API.</span></span>  
  
 <span data-ttu-id="539bd-106">Concetto di base, LINQ to Objects rappresenta un nuovo approccio alle raccolte.</span><span class="sxs-lookup"><span data-stu-id="539bd-106">In a basic sense, LINQ to Objects represents a new approach to collections.</span></span> <span data-ttu-id="539bd-107">In passato, era necessario scrivere cicli `For Each` complessi che specificavano come recuperare i dati da una raccolta.</span><span class="sxs-lookup"><span data-stu-id="539bd-107">In the old way, you had to write complex `For Each` loops that specified how to retrieve data from a collection.</span></span> <span data-ttu-id="539bd-108">Nell'approccio LINQ, scrivere codice dichiarativo che descrive ciò che si desidera recuperare.</span><span class="sxs-lookup"><span data-stu-id="539bd-108">In the LINQ approach, you write declarative code that describes what you want to retrieve.</span></span>  
  
 <span data-ttu-id="539bd-109">Inoltre, le query LINQ offrono tre vantaggi principali rispetto alla tradizionale `For Each` cicli:</span><span class="sxs-lookup"><span data-stu-id="539bd-109">In addition, LINQ queries offer three main advantages over traditional `For Each` loops:</span></span>  
  
1.  <span data-ttu-id="539bd-110">Sono più brevi e leggibili, soprattutto quando si filtrano più condizioni.</span><span class="sxs-lookup"><span data-stu-id="539bd-110">They are more concise and readable, especially when filtering multiple conditions.</span></span>  
  
2.  <span data-ttu-id="539bd-111">Forniscono funzioni potenti di filtro, ordinamento e raggruppamento con un codice dell'applicazione minimo.</span><span class="sxs-lookup"><span data-stu-id="539bd-111">They provide powerful filtering, ordering, and grouping capabilities with a minimum of application code.</span></span>  
  
3.  <span data-ttu-id="539bd-112">Possono essere trasferiti in altre origini dati con modifiche minime o nulle.</span><span class="sxs-lookup"><span data-stu-id="539bd-112">They can be ported to other data sources with little or no modification.</span></span>  
  
 <span data-ttu-id="539bd-113">In generale, più è complessa l'operazione da eseguire sui dati, maggiore sarà il vantaggio si potrà trarre dall'utilizzo di LINQ rispetto alle tecniche di iterazione tradizionali.</span><span class="sxs-lookup"><span data-stu-id="539bd-113">In general, the more complex the operation you want to perform on the data, the more benefit you will realize by using LINQ instead of traditional iteration techniques.</span></span>  
  
 <span data-ttu-id="539bd-114">Lo scopo di questa sezione è illustrato l'approccio LINQ con alcuni esempi specificamente selezionati.</span><span class="sxs-lookup"><span data-stu-id="539bd-114">The purpose of this section is to demonstrate the LINQ approach with some select examples.</span></span> <span data-ttu-id="539bd-115">Tali informazioni non devono essere ritenute esaustive.</span><span class="sxs-lookup"><span data-stu-id="539bd-115">It is not intended to be exhaustive.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="539bd-116">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="539bd-116">In This Section</span></span>  
 [<span data-ttu-id="539bd-117">LINQ e stringhe (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="539bd-117">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)  
 <span data-ttu-id="539bd-118">Viene illustrato come utilizzare LINQ per eseguire query e trasformare stringhe e raccolte di stringhe.</span><span class="sxs-lookup"><span data-stu-id="539bd-118">Explains how LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="539bd-119">Include anche collegamenti ad argomenti che illustrano questi principi.</span><span class="sxs-lookup"><span data-stu-id="539bd-119">Also includes links to topics that demonstrate these principles.</span></span>  
  
 [<span data-ttu-id="539bd-120">LINQ e Reflection (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="539bd-120">LINQ and Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-reflection.md)  
 <span data-ttu-id="539bd-121">Collegamenti a un esempio che illustra come LINQ utilizza la reflection.</span><span class="sxs-lookup"><span data-stu-id="539bd-121">Links to a sample that demonstrates how LINQ uses reflection.</span></span>  
  
 [<span data-ttu-id="539bd-122">Directory di File (Visual Basic) e LINQ</span><span class="sxs-lookup"><span data-stu-id="539bd-122">LINQ and File Directories (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)  
 <span data-ttu-id="539bd-123">Viene illustrato come utilizzare LINQ per interagire con i sistemi di file.</span><span class="sxs-lookup"><span data-stu-id="539bd-123">Explains how LINQ can be used to interact with file systems.</span></span> <span data-ttu-id="539bd-124">Include anche collegamenti ad argomenti che illustrano questi concetti.</span><span class="sxs-lookup"><span data-stu-id="539bd-124">Also includes links to topics that demonstrate these concepts.</span></span>  
  
 [<span data-ttu-id="539bd-125">Procedura: eseguire Query su un ArrayList con LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="539bd-125">How to: Query an ArrayList with LINQ (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)  
 <span data-ttu-id="539bd-126">Viene illustrato come eseguire query su un oggetto ArrayList in c#.</span><span class="sxs-lookup"><span data-stu-id="539bd-126">Demonstrates how to query an ArrayList in C#.</span></span>  
  
 [<span data-ttu-id="539bd-127">Procedura: aggiungere metodi personalizzati per le query LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="539bd-127">How to: Add Custom Methods for LINQ Queries (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-add-custom-methods-for-linq-queries.md)  
 <span data-ttu-id="539bd-128">Viene illustrato come estendere il set di metodi che è possibile utilizzare per le query LINQ aggiungendo metodi di estensione per il <xref:System.Collections.Generic.IEnumerable%601>interfaccia.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="539bd-128">Explains how to extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>  
  
 [<span data-ttu-id="539bd-129">Language-Integrated Query (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="539bd-129">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 <span data-ttu-id="539bd-130">Vengono forniti collegamenti ad argomenti che illustrano LINQ e vengono forniti esempi di codice che eseguono query.</span><span class="sxs-lookup"><span data-stu-id="539bd-130">Provides links to topics that explain LINQ and provide examples of code that perform queries.</span></span>
