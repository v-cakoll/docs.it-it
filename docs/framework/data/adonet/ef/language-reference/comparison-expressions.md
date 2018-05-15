---
title: Espressioni di confronto
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec7637a9-01d5-4a95-8bb0-478311cd263b
ms.openlocfilehash: 5d201d331d766d865d0ee7afb164813084fa3651
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="comparison-expressions"></a><span data-ttu-id="58f9e-102">Espressioni di confronto</span><span class="sxs-lookup"><span data-stu-id="58f9e-102">Comparison Expressions</span></span>
<span data-ttu-id="58f9e-103">Un'espressione di confronto consente di verificare se un valore costante, un valore di un proprietà o un risultato di un metodo è uguale a, non uguale a, maggiore di o minore di un altro valore.</span><span class="sxs-lookup"><span data-stu-id="58f9e-103">A comparison expression checks whether a constant value, property value, or method result is equal, not equal, greater than, or less than another value.</span></span> <span data-ttu-id="58f9e-104">Se un particolare confronto non è valido per [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)], viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="58f9e-104">If a particular comparison is not valid for [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)], an exception will be thrown.</span></span> <span data-ttu-id="58f9e-105">Tutti i confronti, sia impliciti che espliciti, richiedono che tutti i componenti possano essere confrontati nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="58f9e-105">All comparisons, both implicit and explicit, require that all components are comparable in the data source.</span></span> <span data-ttu-id="58f9e-106">Le espressioni di confronto vengono spesso usate nelle clausole `Where` per limitare i risultati delle query.</span><span class="sxs-lookup"><span data-stu-id="58f9e-106">Comparison expressions are frequently used in `Where` clauses for restricting the query results.</span></span>  
  
 <span data-ttu-id="58f9e-107">Nell'esempio seguente nella sintassi delle espressioni di query viene illustrata una query che restituisce i risultati in cui il numero dell'ordine di vendita è uguale a "SO43663":</span><span class="sxs-lookup"><span data-stu-id="58f9e-107">The following example in query expression syntax shows a query that returns results where the sales order number is equal to "SO43663":</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#RestrictionExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#restrictionexpression)]
 [!code-vb[DP L2E Conceptual Examples#RestrictionExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#restrictionexpression)]  
  
 <span data-ttu-id="58f9e-108">Nell'esempio seguente nella sintassi delle query basate su metodo viene illustrata una query che restituisce i risultati in cui il numero dell'ordine di vendita è uguale a "SO43663":</span><span class="sxs-lookup"><span data-stu-id="58f9e-108">The following example in method-based query syntax shows a query that returns results where the sales order number is equal to "SO43663":</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#RestrictionExpression_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#restrictionexpression_mq)]
 [!code-vb[DP L2E Conceptual Examples#RestrictionExpression_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#restrictionexpression_mq)]  
  
 <span data-ttu-id="58f9e-109">Nell'esempio seguente nella sintassi delle espressioni di query viene illustrata una query che restituisce informazioni sugli ordini di vendita in cui la data di spedizione è l'8 luglio 2001:</span><span class="sxs-lookup"><span data-stu-id="58f9e-109">The following example in query expression syntax shows a query that returns sales order information where the ship date is equal to July 8, 2001:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#DateTimeComparison](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#datetimecomparison)]
 [!code-vb[DP L2E Conceptual Examples#DateTimeComparison](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#datetimecomparison)]  
  
 <span data-ttu-id="58f9e-110">Nell'esempio seguente nella sintassi delle query basate su metodo viene illustrata una query che restituisce informazioni sugli ordini di vendita in cui la data di spedizione è l'8 luglio 2001:</span><span class="sxs-lookup"><span data-stu-id="58f9e-110">The following example in method-based query syntax shows a query that returns sales order information where the ship date is equal to July 8, 2001:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#DateTimeComparison_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#datetimecomparison_mq)]
 [!code-vb[DP L2E Conceptual Examples#DateTimeComparison_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#datetimecomparison_mq)]  
  
 <span data-ttu-id="58f9e-111">Le espressioni che producono una costante vengono convertite nel server e non viene eseguito alcun tentativo di valutazione locale.</span><span class="sxs-lookup"><span data-stu-id="58f9e-111">Expressions that yield a constant are converted at the server, and no attempt to do local evaluation is performed.</span></span> <span data-ttu-id="58f9e-112">Nell'esempio seguente viene usata un'espressione nella clausola `Where` che produce una costante.</span><span class="sxs-lookup"><span data-stu-id="58f9e-112">The following example uses an expression in the `Where` clause that yields a constant.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#constantexpression)]
 [!code-vb[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#constantexpression)]  
  
 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]<span data-ttu-id="58f9e-113"> non supporta l'uso di una classe utente come costante.</span><span class="sxs-lookup"><span data-stu-id="58f9e-113"> does not support using a user class as a constant.</span></span> <span data-ttu-id="58f9e-114">Un riferimento a una proprietà in una classe utente è tuttavia considerato una costante e viene convertito in un'espressione costante dell'albero dei comandi ed eseguito nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="58f9e-114">However, a property reference on a user class is considered a constant, and will be converted to a command tree constant expression and executed on the data source.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#MyClass](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#myclass)]
 [!code-vb[DP L2E Conceptual Examples#MyClass](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#myclass)]  
  
 [!code-csharp[DP L2E Conceptual Examples#PropertyAsConstant](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#propertyasconstant)]
 [!code-vb[DP L2E Conceptual Examples#PropertyAsConstant](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#propertyasconstant)]  
  
 <span data-ttu-id="58f9e-115">I metodi che restituiscono un'espressione costante non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="58f9e-115">Methods that return a constant expression are not supported.</span></span> <span data-ttu-id="58f9e-116">Nell'esempio seguente è contenuto un metodo nella clausola `Where` che restituisce una costante.</span><span class="sxs-lookup"><span data-stu-id="58f9e-116">The following example contains a method in the `Where` clause that returns a constant.</span></span> <span data-ttu-id="58f9e-117">Questo esempio provoca la generazione di un'eccezione in fase di runtime.</span><span class="sxs-lookup"><span data-stu-id="58f9e-117">This example will throw an exception at run time.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#MethodAsConstantFails](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#methodasconstantfails)]
 [!code-vb[DP L2E Conceptual Examples#MethodAsConstantFails](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#methodasconstantfails)]  
  
## <a name="see-also"></a><span data-ttu-id="58f9e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58f9e-118">See Also</span></span>  
 [<span data-ttu-id="58f9e-119">Espressioni in query di LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="58f9e-119">Expressions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)
