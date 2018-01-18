---
title: Query di aggregazione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 13ec5580-05ce-4a1f-9d3d-8660be7891a2
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: d4aa6c0a9103bc4a906ecdfb51a55069e6b8b790
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="aggregate-queries"></a><span data-ttu-id="5b956-102">Query di aggregazione</span><span class="sxs-lookup"><span data-stu-id="5b956-102">Aggregate Queries</span></span>
<span data-ttu-id="5b956-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sono supportati gli operatori di aggregazione `Average`, `Count`, `Max`, `Min` e `Sum`.</span><span class="sxs-lookup"><span data-stu-id="5b956-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supports the `Average`, `Count`, `Max`, `Min`, and `Sum` aggregate operators.</span></span> <span data-ttu-id="5b956-104">Di seguito sono riportate le caratteristiche degli operatori di aggregazione in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="5b956-104">Note the following characteristics of aggregate operators in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span></span>  
  
-   <span data-ttu-id="5b956-105">Le query di aggregazione vengono eseguite immediatamente.</span><span class="sxs-lookup"><span data-stu-id="5b956-105">Aggregate queries are executed immediately.</span></span>  
  
     <span data-ttu-id="5b956-106">Per altre informazioni, vedere [Introduzione alle query LINQ (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="5b956-106">For more information, see [Introduction to LINQ Queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
-   <span data-ttu-id="5b956-107">Le query di aggregazione restituiscono in genere un numero anziché una raccolta.</span><span class="sxs-lookup"><span data-stu-id="5b956-107">Aggregate queries typically return a number instead of a collection.</span></span>  
  
     <span data-ttu-id="5b956-108">Per ulteriori informazioni, vedere [operazioni di aggregazione](http://msdn.microsoft.com/library/36d97c83-5de5-457d-971d-10a69365e7c4).</span><span class="sxs-lookup"><span data-stu-id="5b956-108">For more information, see [Aggregation Operations](http://msdn.microsoft.com/library/36d97c83-5de5-457d-971d-10a69365e7c4).</span></span>  
  
-   <span data-ttu-id="5b956-109">Non è possibile chiamare aggregati per tipi anonimi.</span><span class="sxs-lookup"><span data-stu-id="5b956-109">You cannot call aggregates against anonymous types.</span></span>  
  
 <span data-ttu-id="5b956-110">Gli esempi negli argomenti riportati di seguito derivano dal database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="5b956-110">The examples in the following topics derive from the Northwind sample database.</span></span> <span data-ttu-id="5b956-111">Per ulteriori informazioni, vedere [download dei database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="5b956-111">For more information, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5b956-112">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="5b956-112">In This Section</span></span>  
 [<span data-ttu-id="5b956-113">Restituire il valore medio da una sequenza numerica</span><span class="sxs-lookup"><span data-stu-id="5b956-113">Return the Average Value From a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-average-value-from-a-numeric-sequence.md)  
 <span data-ttu-id="5b956-114">Viene illustrato come usare l'operatore <xref:System.Linq.Enumerable.Average%2A>.</span><span class="sxs-lookup"><span data-stu-id="5b956-114">Demonstrates how to use the <xref:System.Linq.Enumerable.Average%2A> operator.</span></span>  
  
 [<span data-ttu-id="5b956-115">Contare il numero di elementi in una sequenza</span><span class="sxs-lookup"><span data-stu-id="5b956-115">Count the Number of Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/count-the-number-of-elements-in-a-sequence.md)  
 <span data-ttu-id="5b956-116">Viene illustrato come usare l'operatore <xref:System.Linq.Enumerable.Count%2A>.</span><span class="sxs-lookup"><span data-stu-id="5b956-116">Demonstrates how to use the <xref:System.Linq.Enumerable.Count%2A> operator.</span></span>  
  
 [<span data-ttu-id="5b956-117">Trovare il valore massimo in una sequenza numerica</span><span class="sxs-lookup"><span data-stu-id="5b956-117">Find the Maximum Value in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/find-the-maximum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="5b956-118">Viene illustrato come usare l'operatore <xref:System.Linq.Enumerable.Max%2A>.</span><span class="sxs-lookup"><span data-stu-id="5b956-118">Demonstrates how to use the <xref:System.Linq.Enumerable.Max%2A> operator.</span></span>  
  
 [<span data-ttu-id="5b956-119">Trovare il valore minimo in una sequenza numerica</span><span class="sxs-lookup"><span data-stu-id="5b956-119">Find the Minimum Value in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/find-the-minimum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="5b956-120">Viene illustrato come usare l'operatore <xref:System.Linq.Enumerable.Min%2A>.</span><span class="sxs-lookup"><span data-stu-id="5b956-120">Demonstrates how to use the <xref:System.Linq.Enumerable.Min%2A> operator.</span></span>  
  
 [<span data-ttu-id="5b956-121">Calcolare la somma dei valori in una sequenza numerica</span><span class="sxs-lookup"><span data-stu-id="5b956-121">Compute the Sum of Values in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)  
 <span data-ttu-id="5b956-122">Viene illustrato come usare l'operatore <xref:System.Linq.Enumerable.Sum%2A>.</span><span class="sxs-lookup"><span data-stu-id="5b956-122">Demonstrates how to use the <xref:System.Linq.Enumerable.Sum%2A> operator.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5b956-123">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="5b956-123">Related Sections</span></span>  
 [<span data-ttu-id="5b956-124">Esempi di query</span><span class="sxs-lookup"><span data-stu-id="5b956-124">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 <span data-ttu-id="5b956-125">Vengono forniti i collegamenti alle query [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] in Visual Basic e C#.</span><span class="sxs-lookup"><span data-stu-id="5b956-125">Provides links to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries in Visual Basic and C#.</span></span>  
  
 [<span data-ttu-id="5b956-126">Concetti relativi alle query</span><span class="sxs-lookup"><span data-stu-id="5b956-126">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 <span data-ttu-id="5b956-127">Vengono forniti i collegamenti ad argomenti in cui sono descritti i concetti per la progettazione di query [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b956-127">Provides links to topics that explain concepts for designing [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="5b956-128">Introduzione alle query LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="5b956-128">Introduction to LINQ Queries (C#)</span></span>](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 <span data-ttu-id="5b956-129">Viene spiegato il funzionamento delle query in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b956-129">Explains how queries work in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span>
