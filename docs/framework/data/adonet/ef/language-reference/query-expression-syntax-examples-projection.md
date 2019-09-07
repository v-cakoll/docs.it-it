---
title: 'Esempi di sintassi delle espressioni di query: Proiezione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 079926c5-e6b5-4fb9-b4cf-9c63886dd626
ms.openlocfilehash: b5139cc310689eb05833ead8d35c03d02eb2fc58
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398424"
---
# <a name="query-expression-syntax-examples-projection"></a><span data-ttu-id="34af6-102">Esempi di sintassi delle espressioni di query: Proiezione</span><span class="sxs-lookup"><span data-stu-id="34af6-102">Query Expression Syntax Examples: Projection</span></span>
<span data-ttu-id="34af6-103">Negli esempi di questo argomento viene illustrato come utilizzare il `Select` metodo e le `From … From …` parole chiave per eseguire una query sul [modello Sales di AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) utilizzando la sintassi delle espressioni di query.</span><span class="sxs-lookup"><span data-stu-id="34af6-103">The examples in this topic demonstrate how to use the `Select` method and the `From … From …` keywords to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using query expression syntax.</span></span> <span data-ttu-id="34af6-104">`From … From …` è l'equivalente basato sulla query del metodo `SelectMany`.</span><span class="sxs-lookup"><span data-stu-id="34af6-104">`From … From …` is the query based equivalent of the `SelectMany` method.</span></span> <span data-ttu-id="34af6-105">Il modello Sales di AdventureWorks usato in questi esempi è compilato in base alle tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="34af6-105">The AdventureWorks Sales model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="34af6-106">Negli esempi di questo argomento vengono utilizzate le `using` istruzioni seguenti: / `Imports`</span><span class="sxs-lookup"><span data-stu-id="34af6-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="select"></a><span data-ttu-id="34af6-107">Select</span><span class="sxs-lookup"><span data-stu-id="34af6-107">Select</span></span>  
  
### <a name="example"></a><span data-ttu-id="34af6-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="34af6-108">Example</span></span>  
 <span data-ttu-id="34af6-109">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Enumerable.Select%2A> per restituire tutte le righe della tabella `Product` e visualizzare i nomi di prodotto.</span><span class="sxs-lookup"><span data-stu-id="34af6-109">The following example uses the <xref:System.Linq.Enumerable.Select%2A> method to return all the rows from the `Product` table and display the product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectSimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple1)]
 [!code-vb[DP L2E Examples#SelectSimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple1)]  
  
### <a name="example"></a><span data-ttu-id="34af6-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="34af6-110">Example</span></span>  
 <span data-ttu-id="34af6-111">Nell'esempio seguente viene usato <xref:System.Linq.Enumerable.Select%2A> per restituire una sequenza dei soli nomi di prodotto.</span><span class="sxs-lookup"><span data-stu-id="34af6-111">The following example uses <xref:System.Linq.Enumerable.Select%2A> to return a sequence of only product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectSimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple2)]
 [!code-vb[DP L2E Examples#SelectSimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple2)]  
  
### <a name="example"></a><span data-ttu-id="34af6-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="34af6-112">Example</span></span>  
 <span data-ttu-id="34af6-113">Nell'esempio seguente viene usato il metodo <xref:System.Linq.Queryable.Select%2A> per proiettare le proprietà `Product.Name` e `Product.ProductID` in una sequenza di tipi anonimi.</span><span class="sxs-lookup"><span data-stu-id="34af6-113">The following example uses the <xref:System.Linq.Queryable.Select%2A> method to project the `Product.Name` and `Product.ProductID` properties into a sequence of anonymous types.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectAnonymousTypes](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectanonymoustypes)]
 [!code-vb[DP L2E Examples#SelectAnonymousTypes](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectanonymoustypes)]  
  
## <a name="from--from--selectmany"></a><span data-ttu-id="34af6-114">Da...</span><span class="sxs-lookup"><span data-stu-id="34af6-114">From …</span></span> <span data-ttu-id="34af6-115">Da...</span><span class="sxs-lookup"><span data-stu-id="34af6-115">From …</span></span> <span data-ttu-id="34af6-116">SelectMany</span><span class="sxs-lookup"><span data-stu-id="34af6-116">(SelectMany)</span></span>  
  
### <a name="example"></a><span data-ttu-id="34af6-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="34af6-117">Example</span></span>  
 <span data-ttu-id="34af6-118">Nell'esempio seguente vengono usate le parole chiave `From … From …`, equivalenti al metodo <xref:System.Linq.Enumerable.SelectMany%2A>, per selezionare tutti gli ordini in cui `TotalDue` è minore di 500,00.</span><span class="sxs-lookup"><span data-stu-id="34af6-118">The following example uses `From … From …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where `TotalDue` is less than 500.00.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom)]  
  
### <a name="example"></a><span data-ttu-id="34af6-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="34af6-119">Example</span></span>  
 <span data-ttu-id="34af6-120">Nell'esempio seguente vengono usate le  parole chiave `From … From …`, equivalenti al metodo <xref:System.Linq.Enumerable.SelectMany%2A>, per selezionare tutti gli ordini effettuati a partire dall'1 ottobre 2002.</span><span class="sxs-lookup"><span data-stu-id="34af6-120">The following example uses `From … From …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where the order was made on October 1, 2002 or later.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom2)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom2)]  
  
### <a name="example"></a><span data-ttu-id="34af6-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="34af6-121">Example</span></span>  
 <span data-ttu-id="34af6-122">Nell'esempio seguente vengono usate le parole chiave `From … From …`, equivalenti al metodo <xref:System.Linq.Enumerable.SelectMany%2A>, per selezionare tutti gli ordini il cui totale è maggiore di 10000,00 e viene usata l'assegnazione `From` per evitare di richiedere due volte il totale.</span><span class="sxs-lookup"><span data-stu-id="34af6-122">The following example uses a `From … From …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where the order total is greater than 10000.00 and uses `From` assignment to avoid requesting the total twice.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyFromAssignment](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanyfromassignment)]
 [!code-vb[DP L2E Examples#SelectManyFromAssignment](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanyfromassignment)]  
  
## <a name="see-also"></a><span data-ttu-id="34af6-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34af6-123">See also</span></span>

- [<span data-ttu-id="34af6-124">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="34af6-124">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
