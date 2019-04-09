---
title: 'Esempi di sintassi delle query basate su metodo: Proiezione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 505491fa-5920-43ce-8a96-c25389e125d8
ms.openlocfilehash: a38fce33fe34bf6485d0d5fcef4f194f4c2470b5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59194994"
---
# <a name="method-based-query-syntax-examples-projection"></a><span data-ttu-id="501b5-102">Esempi di sintassi delle query basate su metodo: Proiezione</span><span class="sxs-lookup"><span data-stu-id="501b5-102">Method-Based Query Syntax Examples: Projection</span></span>
<span data-ttu-id="501b5-103">Gli esempi in questo argomento illustrano come usare il <xref:System.Linq.Enumerable.Select%2A> e <xref:System.Linq.Enumerable.SelectMany%2A> metodi per eseguire una query il [modello Sales di AdventureWorks](https://archive.codeplex.com/?p=msftdbprodsamples) usando la sintassi di query basate su metodo.</span><span class="sxs-lookup"><span data-stu-id="501b5-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Select%2A> and <xref:System.Linq.Enumerable.SelectMany%2A> methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using method-based query syntax.</span></span> <span data-ttu-id="501b5-104">Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="501b5-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="501b5-105">Gli esempi in questo argomento usano il comando seguente `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="501b5-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="select"></a><span data-ttu-id="501b5-106">Seleziona</span><span class="sxs-lookup"><span data-stu-id="501b5-106">Select</span></span>  
  
### <a name="example"></a><span data-ttu-id="501b5-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="501b5-107">Example</span></span>  
 <span data-ttu-id="501b5-108">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Queryable.Select%2A> per proiettare le proprietà `Product.Name` e `Product.ProductID` in una sequenza di tipi anonimi.</span><span class="sxs-lookup"><span data-stu-id="501b5-108">The following example uses the <xref:System.Linq.Queryable.Select%2A> method to project the `Product.Name` and `Product.ProductID` properties into a sequence of anonymous types.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectAnonymousTypes_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectanonymoustypes_mq)]
 [!code-vb[DP L2E Examples#SelectAnonymousTypes_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectanonymoustypes_mq)]  
  
### <a name="example"></a><span data-ttu-id="501b5-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="501b5-109">Example</span></span>  
 <span data-ttu-id="501b5-110">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.Select%2A> per restituire una sequenza dei soli nomi di prodotto.</span><span class="sxs-lookup"><span data-stu-id="501b5-110">The following example uses the <xref:System.Linq.Enumerable.Select%2A> method to return a sequence of only product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectSimple2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple2_mq)]
 [!code-vb[DP L2E Examples#SelectSimple2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple2_mq)]  
  
## <a name="selectmany"></a><span data-ttu-id="501b5-111">SelectMany</span><span class="sxs-lookup"><span data-stu-id="501b5-111">SelectMany</span></span>  
  
### <a name="example"></a><span data-ttu-id="501b5-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="501b5-112">Example</span></span>  
 <span data-ttu-id="501b5-113">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.SelectMany%2A> per selezionare tutti gli ordini in cui `TotalDue` è minore di 500,00.</span><span class="sxs-lookup"><span data-stu-id="501b5-113">The following example uses the <xref:System.Linq.Enumerable.SelectMany%2A> method to select all orders where `TotalDue` is less than 500.00.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom_mq)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom_mq)]  
  
### <a name="example"></a><span data-ttu-id="501b5-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="501b5-114">Example</span></span>  
 <span data-ttu-id="501b5-115">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.SelectMany%2A> per selezionare tutti gli ordini effettuati a partire dall'1 ottobre 2002.</span><span class="sxs-lookup"><span data-stu-id="501b5-115">The following example uses the <xref:System.Linq.Enumerable.SelectMany%2A> method to select all orders where the order was made on October 1, 2002 or later.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom2_mq)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom2_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="501b5-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="501b5-116">See also</span></span>

- [<span data-ttu-id="501b5-117">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="501b5-117">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
