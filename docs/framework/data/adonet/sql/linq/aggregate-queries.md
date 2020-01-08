---
title: Query di aggregazione
ms.date: 03/30/2017
ms.assetid: 13ec5580-05ce-4a1f-9d3d-8660be7891a2
ms.openlocfilehash: 8defefb39974bea150fed84b0e7404b43882c41c
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634742"
---
# <a name="aggregate-queries"></a><span data-ttu-id="9acdc-102">Query di aggregazione</span><span class="sxs-lookup"><span data-stu-id="9acdc-102">Aggregate Queries</span></span>
<span data-ttu-id="9acdc-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sono supportati gli operatori di aggregazione `Average`, `Count`, `Max`, `Min` e `Sum`.</span><span class="sxs-lookup"><span data-stu-id="9acdc-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supports the `Average`, `Count`, `Max`, `Min`, and `Sum` aggregate operators.</span></span> <span data-ttu-id="9acdc-104">Di seguito sono riportate le caratteristiche degli operatori di aggregazione in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="9acdc-104">Note the following characteristics of aggregate operators in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span></span>  
  
- <span data-ttu-id="9acdc-105">Le query di aggregazione vengono eseguite immediatamente.</span><span class="sxs-lookup"><span data-stu-id="9acdc-105">Aggregate queries are executed immediately.</span></span>  
  
     <span data-ttu-id="9acdc-106">Per altre informazioni, vedere [Introduzione alle query LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="9acdc-106">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
- <span data-ttu-id="9acdc-107">Le query di aggregazione restituiscono in genere un numero anziché una raccolta.</span><span class="sxs-lookup"><span data-stu-id="9acdc-107">Aggregate queries typically return a number instead of a collection.</span></span>  
  
     <span data-ttu-id="9acdc-108">Per altre informazioni, vedere [operazioni di aggregazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb546138(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="9acdc-108">For more information, see [Aggregation Operations](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb546138(v=vs.120)).</span></span>  
  
- <span data-ttu-id="9acdc-109">Non è possibile chiamare aggregati per tipi anonimi.</span><span class="sxs-lookup"><span data-stu-id="9acdc-109">You cannot call aggregates against anonymous types.</span></span>  
  
 <span data-ttu-id="9acdc-110">Gli esempi negli argomenti riportati di seguito derivano dal database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="9acdc-110">The examples in the following topics derive from the Northwind sample database.</span></span> <span data-ttu-id="9acdc-111">Per ulteriori informazioni, vedere [download di database di esempio](downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="9acdc-111">For more information, see [Downloading Sample Databases](downloading-sample-databases.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9acdc-112">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="9acdc-112">In This Section</span></span>  
 [<span data-ttu-id="9acdc-113">Restituire il valore medio da una sequenza numerica</span><span class="sxs-lookup"><span data-stu-id="9acdc-113">Return the Average Value From a Numeric Sequence</span></span>](return-the-average-value-from-a-numeric-sequence.md)  
 <span data-ttu-id="9acdc-114">Viene illustrato come usare l'operatore <xref:System.Linq.Enumerable.Average%2A>.</span><span class="sxs-lookup"><span data-stu-id="9acdc-114">Demonstrates how to use the <xref:System.Linq.Enumerable.Average%2A> operator.</span></span>  
  
 [<span data-ttu-id="9acdc-115">Contare il numero di elementi in una sequenza</span><span class="sxs-lookup"><span data-stu-id="9acdc-115">Count the Number of Elements in a Sequence</span></span>](count-the-number-of-elements-in-a-sequence.md)  
 <span data-ttu-id="9acdc-116">Viene illustrato come usare l'operatore <xref:System.Linq.Enumerable.Count%2A>.</span><span class="sxs-lookup"><span data-stu-id="9acdc-116">Demonstrates how to use the <xref:System.Linq.Enumerable.Count%2A> operator.</span></span>  
  
 [<span data-ttu-id="9acdc-117">Trovare il valore massimo in una sequenza numerica</span><span class="sxs-lookup"><span data-stu-id="9acdc-117">Find the Maximum Value in a Numeric Sequence</span></span>](find-the-maximum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="9acdc-118">Viene illustrato come usare l'operatore <xref:System.Linq.Enumerable.Max%2A>.</span><span class="sxs-lookup"><span data-stu-id="9acdc-118">Demonstrates how to use the <xref:System.Linq.Enumerable.Max%2A> operator.</span></span>  
  
 [<span data-ttu-id="9acdc-119">Trovare il valore minimo in una sequenza numerica</span><span class="sxs-lookup"><span data-stu-id="9acdc-119">Find the Minimum Value in a Numeric Sequence</span></span>](find-the-minimum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="9acdc-120">Viene illustrato come usare l'operatore <xref:System.Linq.Enumerable.Min%2A>.</span><span class="sxs-lookup"><span data-stu-id="9acdc-120">Demonstrates how to use the <xref:System.Linq.Enumerable.Min%2A> operator.</span></span>  
  
 [<span data-ttu-id="9acdc-121">Calcolare la somma dei valori in una sequenza numerica</span><span class="sxs-lookup"><span data-stu-id="9acdc-121">Compute the Sum of Values in a Numeric Sequence</span></span>](compute-the-sum-of-values-in-a-numeric-sequence.md)  
 <span data-ttu-id="9acdc-122">Viene illustrato come usare l'operatore <xref:System.Linq.Enumerable.Sum%2A>.</span><span class="sxs-lookup"><span data-stu-id="9acdc-122">Demonstrates how to use the <xref:System.Linq.Enumerable.Sum%2A> operator.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9acdc-123">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="9acdc-123">Related Sections</span></span>  
 [<span data-ttu-id="9acdc-124">Esempi di query</span><span class="sxs-lookup"><span data-stu-id="9acdc-124">Query Examples</span></span>](query-examples.md)  
 <span data-ttu-id="9acdc-125">Vengono forniti i collegamenti alle query [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] in Visual Basic e C#.</span><span class="sxs-lookup"><span data-stu-id="9acdc-125">Provides links to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries in Visual Basic and C#.</span></span>  
  
 [<span data-ttu-id="9acdc-126">Concetti relativi alle query</span><span class="sxs-lookup"><span data-stu-id="9acdc-126">Query Concepts</span></span>](query-concepts.md)  
 <span data-ttu-id="9acdc-127">Vengono forniti collegamenti ad argomenti che illustrano i concetti per la progettazione di query LINQ in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9acdc-127">Provides links to topics that explain concepts for designing LINQ queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="9acdc-128">Introduzione alle query LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="9acdc-128">Introduction to LINQ Queries (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 <span data-ttu-id="9acdc-129">Viene illustrato il funzionamento delle query in LINQ.</span><span class="sxs-lookup"><span data-stu-id="9acdc-129">Explains how queries work in LINQ.</span></span>
