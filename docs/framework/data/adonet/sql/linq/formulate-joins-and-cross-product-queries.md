---
title: Formulare query su prodotto incrociato e join
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 703823368f451839304ce02ff8b5f7259a44b935
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="formulate-joins-and-cross-product-queries"></a><span data-ttu-id="cba43-102">Formulare query su prodotto incrociato e join</span><span class="sxs-lookup"><span data-stu-id="cba43-102">Formulate Joins and Cross-Product Queries</span></span>
<span data-ttu-id="cba43-103">Negli esempi riportati di seguito viene illustrato come combinare risultati da più tabelle.</span><span class="sxs-lookup"><span data-stu-id="cba43-103">The following examples show how to combine results from multiple tables.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cba43-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="cba43-104">Example</span></span>  
 <span data-ttu-id="cba43-105">L'esempio seguente usa la navigazione con chiave esterna nel `From` clausola [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`from` clausola in c#) per selezionare tutti gli ordini per i clienti di Londra.</span><span class="sxs-lookup"><span data-stu-id="cba43-105">The following example uses foreign key navigation in the `From` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`from` clause in C#) to select all orders for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## <a name="example"></a><span data-ttu-id="cba43-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="cba43-106">Example</span></span>  
 <span data-ttu-id="cba43-107">L'esempio seguente usa la navigazione con chiave esterna nel `Where` clausola [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`where` clausola in c#) per filtrare per out-of-stock `Products` cui `Supplier` è negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="cba43-107">The following example uses foreign key navigation in the `Where` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`where` clause in C#) to filter for out-of-stock `Products` whose `Supplier` is in the United States.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## <a name="example"></a><span data-ttu-id="cba43-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="cba43-108">Example</span></span>  
 <span data-ttu-id="cba43-109">Nell'esempio seguente viene usata la navigazione con chiave esterna nella clausola `From` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (la clausola `from` in C#) per filtrare i dipendenti di Seattle ed elencare i territori.</span><span class="sxs-lookup"><span data-stu-id="cba43-109">The following example uses foreign key navigation in the `From` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`from` clause in C#) to filter for employees in Seattle and to list their territories.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## <a name="example"></a><span data-ttu-id="cba43-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="cba43-110">Example</span></span>  
 <span data-ttu-id="cba43-111">L'esempio seguente usa la navigazione con chiave esterna nel `Select` clausola [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clausola in c#) per filtrare le coppie di dipendenti in cui un dipendente riporta a altro ed entrambi sono della stessa `City`.</span><span class="sxs-lookup"><span data-stu-id="cba43-111">The following example uses foreign key navigation in the `Select` clause in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` clause in C#) to filter for pairs of employees where one employee reports to the other and where both employees are from the same `City`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## <a name="example"></a><span data-ttu-id="cba43-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="cba43-112">Example</span></span>  
 <span data-ttu-id="cba43-113">Le operazioni seguenti [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] esempio cerca tutti i clienti e ordini, viene controllato che gli ordini siano associati ai clienti e garantisce che per ogni cliente nell'elenco, viene fornito un nome di contatto.</span><span class="sxs-lookup"><span data-stu-id="cba43-113">The following [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] example looks for all customers and orders, makes sure that the orders are matched to customers, and guarantees that for every customer in that list, a contact name is provided.</span></span>  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## <a name="example"></a><span data-ttu-id="cba43-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="cba43-114">Example</span></span>  
 <span data-ttu-id="cba43-115">Nell'esempio seguente vengono unite in join in modo esplicito due tabelle e vengono proiettati i risultati da entrambe le tabelle.</span><span class="sxs-lookup"><span data-stu-id="cba43-115">The following example explicitly joins two tables and projects results from both tables.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## <a name="example"></a><span data-ttu-id="cba43-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="cba43-116">Example</span></span>  
 <span data-ttu-id="cba43-117">Nell'esempio seguente vengono unite in join in modo esplicito tre tabelle e vengono proiettati i risultati da ogni tabella.</span><span class="sxs-lookup"><span data-stu-id="cba43-117">The following example explicitly joins three tables and projects results from each of them.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## <a name="example"></a><span data-ttu-id="cba43-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="cba43-118">Example</span></span>  
 <span data-ttu-id="cba43-119">Nell'esempio seguente viene illustrato come ottenere `LEFT OUTER JOIN` usando `DefaultIfEmpty()`.</span><span class="sxs-lookup"><span data-stu-id="cba43-119">The following example shows how to achieve a `LEFT OUTER JOIN` by using `DefaultIfEmpty()`.</span></span> <span data-ttu-id="cba43-120">Il metodo `DefaultIfEmpty()` restituisce null se non è presente alcun `Order` per `Employee`.</span><span class="sxs-lookup"><span data-stu-id="cba43-120">The `DefaultIfEmpty()` method returns null when there is no `Order` for the `Employee`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## <a name="example"></a><span data-ttu-id="cba43-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="cba43-121">Example</span></span>  
 <span data-ttu-id="cba43-122">Nell'esempio seguente viene proiettata l'espressione `let` risultante da un join.</span><span class="sxs-lookup"><span data-stu-id="cba43-122">The following example projects a `let` expression resulting from a join.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## <a name="example"></a><span data-ttu-id="cba43-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="cba43-123">Example</span></span>  
 <span data-ttu-id="cba43-124">Nell'esempio seguente viene illustrato un `join` con una chiave composita.</span><span class="sxs-lookup"><span data-stu-id="cba43-124">The following example shows a `join` with a composite key.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## <a name="example"></a><span data-ttu-id="cba43-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="cba43-125">Example</span></span>  
 <span data-ttu-id="cba43-126">Nell'esempio seguente viene descritto come costruire un `join` in cui un solo lato è nullable.</span><span class="sxs-lookup"><span data-stu-id="cba43-126">The following example shows how to construct a `join` where one side is nullable and the other is not.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="cba43-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cba43-127">See Also</span></span>  
 [<span data-ttu-id="cba43-128">Esempi di query</span><span class="sxs-lookup"><span data-stu-id="cba43-128">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
