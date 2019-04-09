---
title: Espressioni in query di LINQ to Entities
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d70b502f-6a15-4120-b4fe-500b173ad9cc
ms.openlocfilehash: 234b3059f9109c23b8ecae4da37e15f7f094fbd1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203236"
---
# <a name="expressions-in-linq-to-entities-queries"></a><span data-ttu-id="e02ca-102">Espressioni in query di LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="e02ca-102">Expressions in LINQ to Entities Queries</span></span>
<span data-ttu-id="e02ca-103">Un'espressione è un frammento di codice che può restituire un singolo valore, oggetto, metodo o spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="e02ca-103">An expression is a fragment of code that can be evaluated to a single value, object, method, or namespace.</span></span> <span data-ttu-id="e02ca-104">Le espressioni possono contenere un valore letterale, una chiamata al metodo, un operatore e i relativi operandi oppure un nome semplice,</span><span class="sxs-lookup"><span data-stu-id="e02ca-104">Expressions can contain a literal value, a method call, an operator and its operands, or a simple name.</span></span> <span data-ttu-id="e02ca-105">ad esempio il nome di una variabile, un membro di un tipo, un parametro di un metodo, uno spazio dei nomi o un tipo.</span><span class="sxs-lookup"><span data-stu-id="e02ca-105">Simple names can be the name of a variable, type member, method parameter, namespace or type.</span></span> <span data-ttu-id="e02ca-106">Le espressioni possono usare operatori che a loro volta usano altre espressioni come parametri oppure chiamate a metodi i cui parametri sono a loro volta altre chiamate a metodi.</span><span class="sxs-lookup"><span data-stu-id="e02ca-106">Expressions can use operators that in turn use other expressions as parameters, or method calls whose parameters are in turn other method calls.</span></span> <span data-ttu-id="e02ca-107">Le espressioni possono pertanto essere da semplici a molto complesse.</span><span class="sxs-lookup"><span data-stu-id="e02ca-107">Therefore, expressions can range from simple to very complex.</span></span>  
  
 <span data-ttu-id="e02ca-108">Nelle [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] query, le espressioni possono contenere qualsiasi elemento consentito dai tipi all'interno di <xref:System.Linq.Expressions> dello spazio dei nomi, tra cui espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="e02ca-108">In [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries, expressions can contain anything allowed by the types within the <xref:System.Linq.Expressions> namespace, including lambda expressions.</span></span> <span data-ttu-id="e02ca-109">Le espressioni che possono essere usate nelle query [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] sono un superset delle espressioni che possono essere usate per eseguire query su [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e02ca-109">The expressions that can be used in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries are a superset of the expressions that can be used to query the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="e02ca-110">Le espressioni che fanno parte di query sul [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] sono limitate a operazioni supportate dal `ObjectQuery<T>` e l'origine dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="e02ca-110">Expressions that are part of queries against the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] are limited to operations supported by `ObjectQuery<T>` and the underlying data source.</span></span>  
  
 <span data-ttu-id="e02ca-111">Nell'esempio seguente il confronto nella clausola `Where` è un'espressione:</span><span class="sxs-lookup"><span data-stu-id="e02ca-111">In the following example, the comparison in the `Where` clause is an expression:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
>  <span data-ttu-id="e02ca-112">I costrutti di linguaggio specifici, ad esempio `unchecked` C#, non hanno significato in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e02ca-112">Specific language constructs, such as C# `unchecked`, have no meaning in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e02ca-113">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="e02ca-113">In This Section</span></span>  
 [<span data-ttu-id="e02ca-114">Espressioni costanti</span><span class="sxs-lookup"><span data-stu-id="e02ca-114">Constant Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constant-expressions.md)  
  
 [<span data-ttu-id="e02ca-115">Espressioni di confronto</span><span class="sxs-lookup"><span data-stu-id="e02ca-115">Comparison Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-expressions.md)  
  
 [<span data-ttu-id="e02ca-116">Confronti Null</span><span class="sxs-lookup"><span data-stu-id="e02ca-116">Null Comparisons</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/null-comparisons.md)  
  
 [<span data-ttu-id="e02ca-117">Espressioni di inizializzazione</span><span class="sxs-lookup"><span data-stu-id="e02ca-117">Initialization Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/initialization-expressions.md)  
  
 [<span data-ttu-id="e02ca-118">Le relazioni, le proprietà di navigazione e le chiavi esterne</span><span class="sxs-lookup"><span data-stu-id="e02ca-118">Relationships, navigation properties and foreign keys</span></span>](/ef/ef6/fundamentals/relationships)  
  
## <a name="see-also"></a><span data-ttu-id="e02ca-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e02ca-119">See also</span></span>

- [<span data-ttu-id="e02ca-120">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="e02ca-120">ADO.NET Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/index.md)
