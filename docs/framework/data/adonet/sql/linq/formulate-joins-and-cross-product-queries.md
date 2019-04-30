---
title: Formulare query su prodotto incrociato e join
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
ms.openlocfilehash: b0037f56947a86627ee9ea84369527aec859a0f8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032604"
---
# <a name="formulate-joins-and-cross-product-queries"></a><span data-ttu-id="19cd6-102">Formulare query su prodotto incrociato e join</span><span class="sxs-lookup"><span data-stu-id="19cd6-102">Formulate Joins and Cross-Product Queries</span></span>
<span data-ttu-id="19cd6-103">Negli esempi riportati di seguito viene illustrato come combinare risultati da più tabelle.</span><span class="sxs-lookup"><span data-stu-id="19cd6-103">The following examples show how to combine results from multiple tables.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19cd6-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="19cd6-104">Example</span></span>  
 <span data-ttu-id="19cd6-105">L'esempio seguente usa navigazione con chiave esterna nel `From` clausola in Visual Basic (`from` clausola in C#) per selezionare tutti gli ordini per i clienti di Londra.</span><span class="sxs-lookup"><span data-stu-id="19cd6-105">The following example uses foreign key navigation in the `From` clause in Visual Basic (`from` clause in C#) to select all orders for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## <a name="example"></a><span data-ttu-id="19cd6-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="19cd6-106">Example</span></span>  
 <span data-ttu-id="19cd6-107">L'esempio seguente usa navigazione con chiave esterna nel `Where` clausola in Visual Basic (`where` clausola in C#) per filtrare per out-of-stock `Products` cui `Supplier` è negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="19cd6-107">The following example uses foreign key navigation in the `Where` clause in Visual Basic (`where` clause in C#) to filter for out-of-stock `Products` whose `Supplier` is in the United States.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## <a name="example"></a><span data-ttu-id="19cd6-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="19cd6-108">Example</span></span>  
 <span data-ttu-id="19cd6-109">L'esempio seguente usa navigazione con chiave esterna nel `From` clausola in Visual Basic (`from` clausola in C#) per filtrare i dipendenti di Seattle ed elencare i territori.</span><span class="sxs-lookup"><span data-stu-id="19cd6-109">The following example uses foreign key navigation in the `From` clause in Visual Basic (`from` clause in C#) to filter for employees in Seattle and to list their territories.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## <a name="example"></a><span data-ttu-id="19cd6-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="19cd6-110">Example</span></span>  
 <span data-ttu-id="19cd6-111">L'esempio seguente usa navigazione con chiave esterna nel `Select` clausola in Visual Basic (`select` clausola in C#) per filtrare le coppie di dipendenti in cui un dipendente riporta a altro ed entrambi sono della stessa `City`.</span><span class="sxs-lookup"><span data-stu-id="19cd6-111">The following example uses foreign key navigation in the `Select` clause in Visual Basic (`select` clause in C#) to filter for pairs of employees where one employee reports to the other and where both employees are from the same `City`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## <a name="example"></a><span data-ttu-id="19cd6-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="19cd6-112">Example</span></span>  
 <span data-ttu-id="19cd6-113">Nell'esempio Visual Basic seguente cerca tutti i clienti e ordini, assicura che gli ordini sono associati ai clienti e garantisce che per ogni cliente nell'elenco, viene fornito un nome di contatto.</span><span class="sxs-lookup"><span data-stu-id="19cd6-113">The following Visual Basic example looks for all customers and orders, makes sure that the orders are matched to customers, and guarantees that for every customer in that list, a contact name is provided.</span></span>  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## <a name="example"></a><span data-ttu-id="19cd6-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="19cd6-114">Example</span></span>  
 <span data-ttu-id="19cd6-115">Nell'esempio seguente vengono unite in join in modo esplicito due tabelle e vengono proiettati i risultati da entrambe le tabelle.</span><span class="sxs-lookup"><span data-stu-id="19cd6-115">The following example explicitly joins two tables and projects results from both tables.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## <a name="example"></a><span data-ttu-id="19cd6-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="19cd6-116">Example</span></span>  
 <span data-ttu-id="19cd6-117">Nell'esempio seguente vengono unite in join in modo esplicito tre tabelle e vengono proiettati i risultati da ogni tabella.</span><span class="sxs-lookup"><span data-stu-id="19cd6-117">The following example explicitly joins three tables and projects results from each of them.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## <a name="example"></a><span data-ttu-id="19cd6-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="19cd6-118">Example</span></span>  
 <span data-ttu-id="19cd6-119">Nell'esempio seguente viene illustrato come ottenere `LEFT OUTER JOIN` usando `DefaultIfEmpty()`.</span><span class="sxs-lookup"><span data-stu-id="19cd6-119">The following example shows how to achieve a `LEFT OUTER JOIN` by using `DefaultIfEmpty()`.</span></span> <span data-ttu-id="19cd6-120">Il metodo `DefaultIfEmpty()` restituisce null se non è presente alcun `Order` per `Employee`.</span><span class="sxs-lookup"><span data-stu-id="19cd6-120">The `DefaultIfEmpty()` method returns null when there is no `Order` for the `Employee`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## <a name="example"></a><span data-ttu-id="19cd6-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="19cd6-121">Example</span></span>  
 <span data-ttu-id="19cd6-122">Nell'esempio seguente viene proiettata l'espressione `let` risultante da un join.</span><span class="sxs-lookup"><span data-stu-id="19cd6-122">The following example projects a `let` expression resulting from a join.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## <a name="example"></a><span data-ttu-id="19cd6-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="19cd6-123">Example</span></span>  
 <span data-ttu-id="19cd6-124">Nell'esempio seguente viene illustrato un `join` con una chiave composita.</span><span class="sxs-lookup"><span data-stu-id="19cd6-124">The following example shows a `join` with a composite key.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## <a name="example"></a><span data-ttu-id="19cd6-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="19cd6-125">Example</span></span>  
 <span data-ttu-id="19cd6-126">Nell'esempio seguente viene descritto come costruire un `join` in cui un solo lato è nullable.</span><span class="sxs-lookup"><span data-stu-id="19cd6-126">The following example shows how to construct a `join` where one side is nullable and the other is not.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="19cd6-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19cd6-127">See also</span></span>

- [<span data-ttu-id="19cd6-128">Esempi di query</span><span class="sxs-lookup"><span data-stu-id="19cd6-128">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
