---
title: Esempi di query
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 137f8677-494c-4d49-95ce-c17742f2d01f
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 1b3aabf5a47088fa408547527c5f18fa69a48e02
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="query-examples"></a><span data-ttu-id="12489-102">Esempi di query</span><span class="sxs-lookup"><span data-stu-id="12489-102">Query Examples</span></span>
<span data-ttu-id="12489-103">Contenuto della sezione vengono forniti esempi di query [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] tipiche per [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] e C#.</span><span class="sxs-lookup"><span data-stu-id="12489-103">This section provides [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] and C# examples of typical [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries.</span></span> <span data-ttu-id="12489-104">Gli sviluppatori che usano [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] possono trovare ulteriori esempi in una soluzione di esempio disponibile nella sezione Esempi.</span><span class="sxs-lookup"><span data-stu-id="12489-104">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can find many more examples in a sample solution available in the Samples section.</span></span> <span data-ttu-id="12489-105">Per ulteriori informazioni, vedere [esempi](../../../../../../docs/framework/data/adonet/sql/linq/samples.md).</span><span class="sxs-lookup"><span data-stu-id="12489-105">For more information, see [Samples](../../../../../../docs/framework/data/adonet/sql/linq/samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="12489-106">*DB* viene spesso usato negli esempi di codice in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentazione.</span><span class="sxs-lookup"><span data-stu-id="12489-106">*db* is often used in code examples in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation.</span></span> <span data-ttu-id="12489-107">*DB* si presuppone che sia un'istanza di un *Northwind* (classe), che eredita da <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="12489-107">*db* is assumed to be an instance of a *Northwind* class, which inherits from <xref:System.Data.Linq.DataContext>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="12489-108">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="12489-108">In This Section</span></span>  
 [<span data-ttu-id="12489-109">Query di aggregazione</span><span class="sxs-lookup"><span data-stu-id="12489-109">Aggregate Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 <span data-ttu-id="12489-110">Viene descritto come usare <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A> e così via.</span><span class="sxs-lookup"><span data-stu-id="12489-110">Describes how to use <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, and so forth.</span></span>  
  
 [<span data-ttu-id="12489-111">Restituire il primo elemento di una sequenza</span><span class="sxs-lookup"><span data-stu-id="12489-111">Return the First Element in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-first-element-in-a-sequence.md)  
 <span data-ttu-id="12489-112">Vengono forniti esempi dell'utilizzo di <xref:System.Linq.Enumerable.First%2A>.</span><span class="sxs-lookup"><span data-stu-id="12489-112">Provides examples of using <xref:System.Linq.Enumerable.First%2A>.</span></span>  
  
 [<span data-ttu-id="12489-113">Restituire o ignorare elementi in una sequenza</span><span class="sxs-lookup"><span data-stu-id="12489-113">Return Or Skip Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-or-skip-elements-in-a-sequence.md)  
 <span data-ttu-id="12489-114">Vengono forniti esempi dell'utilizzo di <xref:System.Linq.Enumerable.Take%2A> e <xref:System.Linq.Enumerable.Skip%2A>.</span><span class="sxs-lookup"><span data-stu-id="12489-114">Provides examples of using <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A>.</span></span>  
  
 [<span data-ttu-id="12489-115">Ordinare elementi in una sequenza</span><span class="sxs-lookup"><span data-stu-id="12489-115">Sort Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sort-elements-in-a-sequence.md)  
 <span data-ttu-id="12489-116">Vengono forniti esempi dell'utilizzo di <xref:System.Linq.Enumerable.OrderBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="12489-116">Provides examples of using <xref:System.Linq.Enumerable.OrderBy%2A>.</span></span>  
  
 [<span data-ttu-id="12489-117">Raggruppare elementi in una sequenza</span><span class="sxs-lookup"><span data-stu-id="12489-117">Group Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/group-elements-in-a-sequence.md)  
 <span data-ttu-id="12489-118">Vengono forniti esempi dell'utilizzo di <xref:System.Linq.Enumerable.GroupBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="12489-118">Provides examples of using <xref:System.Linq.Enumerable.GroupBy%2A>.</span></span>  
  
 [<span data-ttu-id="12489-119">Eliminare elementi duplicati da una sequenza</span><span class="sxs-lookup"><span data-stu-id="12489-119">Eliminate Duplicate Elements from a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/eliminate-duplicate-elements-from-a-sequence.md)  
 <span data-ttu-id="12489-120">Vengono forniti esempi dell'utilizzo di <xref:System.Linq.Enumerable.Distinct%2A>.</span><span class="sxs-lookup"><span data-stu-id="12489-120">Provides examples of using <xref:System.Linq.Enumerable.Distinct%2A>.</span></span>  
  
 [<span data-ttu-id="12489-121">Determinare se alcuni o tutti gli elementi di una sequenza soddisfano una condizione</span><span class="sxs-lookup"><span data-stu-id="12489-121">Determine if Any or All Elements in a Sequence Satisfy a Condition</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition.md)  
 <span data-ttu-id="12489-122">Vengono forniti esempi dell'utilizzo di <xref:System.Linq.Enumerable.All%2A> e <xref:System.Linq.Enumerable.Any%2A>.</span><span class="sxs-lookup"><span data-stu-id="12489-122">Provides examples of using <xref:System.Linq.Enumerable.All%2A> and <xref:System.Linq.Enumerable.Any%2A>.</span></span>  
  
 [<span data-ttu-id="12489-123">Concatenare due sequenze</span><span class="sxs-lookup"><span data-stu-id="12489-123">Concatenate Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/concatenate-two-sequences.md)  
 <span data-ttu-id="12489-124">Vengono forniti esempi dell'utilizzo di <xref:System.Linq.Enumerable.Concat%2A>.</span><span class="sxs-lookup"><span data-stu-id="12489-124">Provides examples of using <xref:System.Linq.Enumerable.Concat%2A>.</span></span>  
  
 [<span data-ttu-id="12489-125">Restituire la differenza dei set tra due sequenze</span><span class="sxs-lookup"><span data-stu-id="12489-125">Return the Set Difference Between Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-difference-between-two-sequences.md)  
 <span data-ttu-id="12489-126">Vengono forniti esempi dell'utilizzo di <xref:System.Linq.Enumerable.Except%2A>.</span><span class="sxs-lookup"><span data-stu-id="12489-126">Provides examples of using <xref:System.Linq.Enumerable.Except%2A>.</span></span>  
  
 [<span data-ttu-id="12489-127">Restituire l'intersezione tra set di due sequenze</span><span class="sxs-lookup"><span data-stu-id="12489-127">Return the Set Intersection of Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-intersection-of-two-sequences.md)  
 <span data-ttu-id="12489-128">Vengono forniti esempi dell'utilizzo di <xref:System.Linq.Enumerable.Intersect%2A>.</span><span class="sxs-lookup"><span data-stu-id="12489-128">Provides examples of using <xref:System.Linq.Enumerable.Intersect%2A>.</span></span>  
  
 [<span data-ttu-id="12489-129">Restituire l'unione di set di due sequenze</span><span class="sxs-lookup"><span data-stu-id="12489-129">Return the Set Union of Two Sequences</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-union-of-two-sequences.md)  
 <span data-ttu-id="12489-130">Vengono forniti esempi dell'utilizzo di <xref:System.Linq.Enumerable.Union%2A>.</span><span class="sxs-lookup"><span data-stu-id="12489-130">Provides examples of using <xref:System.Linq.Enumerable.Union%2A>.</span></span>  
  
 [<span data-ttu-id="12489-131">Procedura: convertire una sequenza in una matrice</span><span class="sxs-lookup"><span data-stu-id="12489-131">Convert a Sequence to an Array</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-sequence-to-an-array.md)  
 <span data-ttu-id="12489-132">Vengono forniti esempi dell'utilizzo di <xref:System.Linq.Enumerable.ToArray%2A>.</span><span class="sxs-lookup"><span data-stu-id="12489-132">Provides examples of using <xref:System.Linq.Enumerable.ToArray%2A>.</span></span>  
  
 [<span data-ttu-id="12489-133">Convertire una sequenza un tipo in un elenco generico</span><span class="sxs-lookup"><span data-stu-id="12489-133">Convert a Sequence to a Generic List</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-sequence-to-a-generic-list.md)  
 <span data-ttu-id="12489-134">Vengono forniti esempi dell'utilizzo di <xref:System.Linq.Enumerable.ToList%2A>.</span><span class="sxs-lookup"><span data-stu-id="12489-134">Provides examples of using <xref:System.Linq.Enumerable.ToList%2A>.</span></span>  
  
 [<span data-ttu-id="12489-135">Convertire un tipo in un IEnumerable generico</span><span class="sxs-lookup"><span data-stu-id="12489-135">Convert a Type to a Generic IEnumerable</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-type-to-a-generic-ienumerable.md)  
 <span data-ttu-id="12489-136">Vengono forniti esempi dell'utilizzo di <xref:System.Linq.Enumerable.AsEnumerable%2A>.</span><span class="sxs-lookup"><span data-stu-id="12489-136">Provides examples of using <xref:System.Linq.Enumerable.AsEnumerable%2A>.</span></span>  
  
 [<span data-ttu-id="12489-137">Formulare join e query di prodotto incrociato</span><span class="sxs-lookup"><span data-stu-id="12489-137">Formulate Joins and Cross-Product Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)  
 <span data-ttu-id="12489-138">Vengono forniti esempi dell'utilizzo della navigazione con chiave esterna nelle clausole `from`, `where` e `select`.</span><span class="sxs-lookup"><span data-stu-id="12489-138">Provides examples of using foreign-key navigation in the `from`, `where`, and `select` clauses.</span></span>  
  
 [<span data-ttu-id="12489-139">Formulare proiezioni</span><span class="sxs-lookup"><span data-stu-id="12489-139">Formulate Projections</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/formulate-projections.md)  
 <span data-ttu-id="12489-140">Vengono forniti esempi della combinazione `select` con altre funzionalità (ad esempio, *tipi anonimi*) per formare proiezioni della query.</span><span class="sxs-lookup"><span data-stu-id="12489-140">Provides examples of combining `select` with other features (for example, *anonymous types*) to form query projections.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="12489-141">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="12489-141">Related Sections</span></span>  
 [<span data-ttu-id="12489-142">Cenni preliminari sugli operatori di query standard</span><span class="sxs-lookup"><span data-stu-id="12489-142">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)  
 <span data-ttu-id="12489-143">Viene illustrato il concetto di operatori di query standard.</span><span class="sxs-lookup"><span data-stu-id="12489-143">Explains the concept of standard query operators.</span></span>  
  
 [<span data-ttu-id="12489-144">Concetti relativi alle query</span><span class="sxs-lookup"><span data-stu-id="12489-144">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 <span data-ttu-id="12489-145">Viene descritto come vengono usati i concetti applicabili alle query in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12489-145">Explains how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] uses concepts that apply to queries.</span></span>  
  
 [<span data-ttu-id="12489-146">Guida per programmatori</span><span class="sxs-lookup"><span data-stu-id="12489-146">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 <span data-ttu-id="12489-147">Viene fornito un portale per accedere ad argomenti in cui vengono illustrati concetti di programmazione relativi a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12489-147">Provides a portal to topics that explain programming concepts related to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>
