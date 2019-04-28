---
title: 'Esempi di sintassi delle espressioni di query: Proiezione (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 48c9f5ed-76bf-4228-ab10-5217bbb295a3
ms.openlocfilehash: 3bd7934cef03df391c1871b8499f911a023d7d3b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61644523"
---
# <a name="query-expression-syntax-examples-projection--linq-to-dataset"></a><span data-ttu-id="4455a-102">Esempi di sintassi delle espressioni di query: Proiezione (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="4455a-102">Query Expression Syntax Examples: Projection  (LINQ to DataSet)</span></span>
<span data-ttu-id="4455a-103">Negli esempi di questo argomento viene illustrato l'uso dei metodi <xref:System.Linq.Enumerable.Select%2A> e <xref:System.Linq.Enumerable.SelectMany%2A> per eseguire una query su <xref:System.Data.DataSet> usando la sintassi delle espressioni di query.</span><span class="sxs-lookup"><span data-stu-id="4455a-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Select%2A> and <xref:System.Linq.Enumerable.SelectMany%2A> methods to query a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="4455a-104">Il `FillDataSet` metodo usato in questi esempi è specificato nel [caricamento dei dati in un set di dati](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="4455a-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="4455a-105">Negli esempi di questo argomento vengono usate le tabelle Contact, Address, Product, SalesOrderHeader e SalesOrderDetail del database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="4455a-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="4455a-106">Gli esempi in questo argomento usano il comando seguente `using` / `Imports` istruzioni:</span><span class="sxs-lookup"><span data-stu-id="4455a-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="4455a-107">Per altre informazioni, vedere [Procedura: Creare un progetto LINQ to DataSet In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="4455a-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="select"></a><span data-ttu-id="4455a-108">Seleziona</span><span class="sxs-lookup"><span data-stu-id="4455a-108">Select</span></span>  
  
### <a name="example"></a><span data-ttu-id="4455a-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="4455a-109">Example</span></span>  
 <span data-ttu-id="4455a-110">In questo esempio viene usato il metodo <xref:System.Linq.Enumerable.Select%2A> per restituire tutte le righe della tabella `Product` e visualizzare i nomi di prodotto.</span><span class="sxs-lookup"><span data-stu-id="4455a-110">This example uses the <xref:System.Linq.Enumerable.Select%2A> method to return all the rows from the `Product` table and display the product names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectSimple1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectsimple1)]
 [!code-vb[DP LINQ to DataSet Examples#SelectSimple1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectsimple1)]  
  
### <a name="example"></a><span data-ttu-id="4455a-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="4455a-111">Example</span></span>  
 <span data-ttu-id="4455a-112">In questo esempio viene usato <xref:System.Linq.Enumerable.Select%2A> per restituire una sequenza dei soli nomi di prodotto.</span><span class="sxs-lookup"><span data-stu-id="4455a-112">This example uses <xref:System.Linq.Enumerable.Select%2A> to return a sequence of only product names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectSimple2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectsimple2)]
 [!code-vb[DP LINQ to DataSet Examples#SelectSimple2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectsimple2)]  
  
## <a name="selectmany"></a><span data-ttu-id="4455a-113">SelectMany</span><span class="sxs-lookup"><span data-stu-id="4455a-113">SelectMany</span></span>  
  
### <a name="example"></a><span data-ttu-id="4455a-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="4455a-114">Example</span></span>  
 <span data-ttu-id="4455a-115">In questo esempio viene usato `From …, …`, l'equivalente del metodo <xref:System.Linq.Enumerable.SelectMany%2A>, per selezionare tutti gli ordini in cui `TotalDue` è minore di 500,00.</span><span class="sxs-lookup"><span data-stu-id="4455a-115">This example uses `From …, …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where `TotalDue` is less than 500.00.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyCompoundFrom](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanycompoundfrom)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyCompoundFrom](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanycompoundfrom)]  
  
### <a name="example"></a><span data-ttu-id="4455a-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="4455a-116">Example</span></span>  
 <span data-ttu-id="4455a-117">In questo esempio viene usato `From …, …`, l'equivalente del metodo <xref:System.Linq.Enumerable.SelectMany%2A>, per selezionare tutti gli ordini che sono stati effettuati a partire dall'1 ottobre 2002.</span><span class="sxs-lookup"><span data-stu-id="4455a-117">This example uses `From …, …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where the order was made on October 1, 2002 or later.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyCompoundFrom2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanycompoundfrom2)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyCompoundFrom2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanycompoundfrom2)]  
  
### <a name="example"></a><span data-ttu-id="4455a-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="4455a-118">Example</span></span>  
 <span data-ttu-id="4455a-119">In questo esempio viene usato `From …, …`, l'equivalente del metodo <xref:System.Linq.Enumerable.SelectMany%2A>, per selezionare tutti gli ordini in cui il totale è maggiore di 10000,00 e viene usata l'assegnazione `From` per evitare di richiedere due volte il totale.</span><span class="sxs-lookup"><span data-stu-id="4455a-119">This example uses a `From …, …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where the order total is greater than 10000.00 and uses `From` assignment to avoid requesting the total twice.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyFromAssignment](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanyfromassignment)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyFromAssignment](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanyfromassignment)]  
  
## <a name="see-also"></a><span data-ttu-id="4455a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4455a-120">See also</span></span>

- [<span data-ttu-id="4455a-121">Caricamento di dati in un oggetto DataSet</span><span class="sxs-lookup"><span data-stu-id="4455a-121">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [<span data-ttu-id="4455a-122">Esempi di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="4455a-122">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [<span data-ttu-id="4455a-123">Panoramica degli operatori di query standard (C#)</span><span class="sxs-lookup"><span data-stu-id="4455a-123">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="4455a-124">Panoramica degli operatori query standard (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4455a-124">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
