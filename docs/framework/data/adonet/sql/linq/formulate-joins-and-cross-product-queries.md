---
title: Formulare query su prodotto incrociato e join
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8072ede-0521-4670-9bec-1778ceeb875b
ms.openlocfilehash: 002a644ff5d48b25351228dcd74330707491d6c8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782085"
---
# <a name="formulate-joins-and-cross-product-queries"></a><span data-ttu-id="bbebf-102">Formulare query su prodotto incrociato e join</span><span class="sxs-lookup"><span data-stu-id="bbebf-102">Formulate Joins and Cross-Product Queries</span></span>
<span data-ttu-id="bbebf-103">Negli esempi riportati di seguito viene illustrato come combinare risultati da più tabelle.</span><span class="sxs-lookup"><span data-stu-id="bbebf-103">The following examples show how to combine results from multiple tables.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bbebf-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="bbebf-104">Example</span></span>  
 <span data-ttu-id="bbebf-105">Nell'esempio seguente viene usata la navigazione con chiave `From` esterna nella clausola in`from` Visual Basic ( C#clausola in) per selezionare tutti gli ordini per i clienti di Londra.</span><span class="sxs-lookup"><span data-stu-id="bbebf-105">The following example uses foreign key navigation in the `From` clause in Visual Basic (`from` clause in C#) to select all orders for customers in London.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#47](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#47)]
 [!code-vb[DLinqQueryExamples#47](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#47)]  
  
## <a name="example"></a><span data-ttu-id="bbebf-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="bbebf-106">Example</span></span>  
 <span data-ttu-id="bbebf-107">Nell'esempio seguente viene usata la navigazione con chiave `Where` esterna nella clausola in`where` Visual Basic ( C#clausola in) per filtrare per l'esaurimento `Products` delle `Supplier` scorte il cui oggetto si trova nel Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="bbebf-107">The following example uses foreign key navigation in the `Where` clause in Visual Basic (`where` clause in C#) to filter for out-of-stock `Products` whose `Supplier` is in the United States.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#48](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#48)]
 [!code-vb[DLinqQueryExamples#48](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#48)]  
  
## <a name="example"></a><span data-ttu-id="bbebf-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="bbebf-108">Example</span></span>  
 <span data-ttu-id="bbebf-109">Nell'esempio seguente viene usata la navigazione con chiave `From` esterna nella clausola in`from` Visual Basic ( C#clausola in) per filtrare i dipendenti a Seattle e per elencarne i territori.</span><span class="sxs-lookup"><span data-stu-id="bbebf-109">The following example uses foreign key navigation in the `From` clause in Visual Basic (`from` clause in C#) to filter for employees in Seattle and to list their territories.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#49](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#49)]  
  
## <a name="example"></a><span data-ttu-id="bbebf-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="bbebf-110">Example</span></span>  
 <span data-ttu-id="bbebf-111">Nell'esempio seguente viene usata la navigazione con chiave `Select` esterna nella clausola in`select` Visual Basic ( C#clausola in) per filtrare le coppie di dipendenti in cui un dipendente segnala l'altro e il punto in cui entrambi `City`i dipendenti sono dallo stesso.</span><span class="sxs-lookup"><span data-stu-id="bbebf-111">The following example uses foreign key navigation in the `Select` clause in Visual Basic (`select` clause in C#) to filter for pairs of employees where one employee reports to the other and where both employees are from the same `City`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#50](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#50)]
 [!code-vb[DLinqQueryExamples#50](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50)]  
  
## <a name="example"></a><span data-ttu-id="bbebf-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="bbebf-112">Example</span></span>  
 <span data-ttu-id="bbebf-113">Nell'esempio di Visual Basic seguente viene eseguita la ricerca di tutti i clienti e gli ordini, verifica che gli ordini vengano abbinati ai clienti e garantisce che per ogni cliente nell'elenco venga fornito un nome di contatto.</span><span class="sxs-lookup"><span data-stu-id="bbebf-113">The following Visual Basic example looks for all customers and orders, makes sure that the orders are matched to customers, and guarantees that for every customer in that list, a contact name is provided.</span></span>  
  
 [!code-vb[DLinqQueryExamples#50v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#50v)]  
  
## <a name="example"></a><span data-ttu-id="bbebf-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="bbebf-114">Example</span></span>  
 <span data-ttu-id="bbebf-115">Nell'esempio seguente vengono unite in join in modo esplicito due tabelle e vengono proiettati i risultati da entrambe le tabelle.</span><span class="sxs-lookup"><span data-stu-id="bbebf-115">The following example explicitly joins two tables and projects results from both tables.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#51](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#51)]
 [!code-vb[DLinqQueryExamples#51](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#51)]  
  
## <a name="example"></a><span data-ttu-id="bbebf-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="bbebf-116">Example</span></span>  
 <span data-ttu-id="bbebf-117">Nell'esempio seguente vengono unite in join in modo esplicito tre tabelle e vengono proiettati i risultati da ogni tabella.</span><span class="sxs-lookup"><span data-stu-id="bbebf-117">The following example explicitly joins three tables and projects results from each of them.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#52](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#52)]
 [!code-vb[DLinqQueryExamples#52](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#52)]  
  
## <a name="example"></a><span data-ttu-id="bbebf-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="bbebf-118">Example</span></span>  
 <span data-ttu-id="bbebf-119">Nell'esempio seguente viene illustrato come ottenere `LEFT OUTER JOIN` usando `DefaultIfEmpty()`.</span><span class="sxs-lookup"><span data-stu-id="bbebf-119">The following example shows how to achieve a `LEFT OUTER JOIN` by using `DefaultIfEmpty()`.</span></span> <span data-ttu-id="bbebf-120">Il metodo `DefaultIfEmpty()` restituisce null se non è presente alcun `Order` per `Employee`.</span><span class="sxs-lookup"><span data-stu-id="bbebf-120">The `DefaultIfEmpty()` method returns null when there is no `Order` for the `Employee`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#53](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#53)]
 [!code-vb[DLinqQueryExamples#53](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#53)]  
  
## <a name="example"></a><span data-ttu-id="bbebf-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="bbebf-121">Example</span></span>  
 <span data-ttu-id="bbebf-122">Nell'esempio seguente viene proiettata l'espressione `let` risultante da un join.</span><span class="sxs-lookup"><span data-stu-id="bbebf-122">The following example projects a `let` expression resulting from a join.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#54](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#54)]
 [!code-vb[DLinqQueryExamples#54](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#54)]  
  
## <a name="example"></a><span data-ttu-id="bbebf-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="bbebf-123">Example</span></span>  
 <span data-ttu-id="bbebf-124">Nell'esempio seguente viene illustrato un `join` con una chiave composita.</span><span class="sxs-lookup"><span data-stu-id="bbebf-124">The following example shows a `join` with a composite key.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#55](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#55)]
 [!code-vb[DLinqQueryExamples#55](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#55)]  
  
## <a name="example"></a><span data-ttu-id="bbebf-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="bbebf-125">Example</span></span>  
 <span data-ttu-id="bbebf-126">Nell'esempio seguente viene descritto come costruire un `join` in cui un solo lato è nullable.</span><span class="sxs-lookup"><span data-stu-id="bbebf-126">The following example shows how to construct a `join` where one side is nullable and the other is not.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#56](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#56)]
 [!code-vb[DLinqQueryExamples#56](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="bbebf-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbebf-127">See also</span></span>

- [<span data-ttu-id="bbebf-128">Esempi di query</span><span class="sxs-lookup"><span data-stu-id="bbebf-128">Query Examples</span></span>](query-examples.md)
