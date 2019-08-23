---
title: Espressioni in query di LINQ to Entities
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d70b502f-6a15-4120-b4fe-500b173ad9cc
ms.openlocfilehash: 383339241194c56d0c3178f538f2ac08b2f1b437
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950396"
---
# <a name="expressions-in-linq-to-entities-queries"></a><span data-ttu-id="4890c-102">Espressioni in query di LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="4890c-102">Expressions in LINQ to Entities Queries</span></span>
<span data-ttu-id="4890c-103">Un'espressione è un frammento di codice che può restituire un singolo valore, oggetto, metodo o spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="4890c-103">An expression is a fragment of code that can be evaluated to a single value, object, method, or namespace.</span></span> <span data-ttu-id="4890c-104">Le espressioni possono contenere un valore letterale, una chiamata al metodo, un operatore e i relativi operandi oppure un nome semplice,</span><span class="sxs-lookup"><span data-stu-id="4890c-104">Expressions can contain a literal value, a method call, an operator and its operands, or a simple name.</span></span> <span data-ttu-id="4890c-105">ad esempio il nome di una variabile, un membro di un tipo, un parametro di un metodo, uno spazio dei nomi o un tipo.</span><span class="sxs-lookup"><span data-stu-id="4890c-105">Simple names can be the name of a variable, type member, method parameter, namespace or type.</span></span> <span data-ttu-id="4890c-106">Le espressioni possono usare operatori che a loro volta usano altre espressioni come parametri oppure chiamate a metodi i cui parametri sono a loro volta altre chiamate a metodi.</span><span class="sxs-lookup"><span data-stu-id="4890c-106">Expressions can use operators that in turn use other expressions as parameters, or method calls whose parameters are in turn other method calls.</span></span> <span data-ttu-id="4890c-107">Le espressioni possono pertanto essere da semplici a molto complesse.</span><span class="sxs-lookup"><span data-stu-id="4890c-107">Therefore, expressions can range from simple to very complex.</span></span>  
  
 <span data-ttu-id="4890c-108">Nelle query LINQ to Entities, le espressioni possono contenere qualsiasi elemento consentito dai tipi all' <xref:System.Linq.Expressions> interno dello spazio dei nomi, incluse le espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="4890c-108">In LINQ to Entities queries, expressions can contain anything allowed by the types within the <xref:System.Linq.Expressions> namespace, including lambda expressions.</span></span> <span data-ttu-id="4890c-109">Le espressioni che possono essere utilizzate nelle query LINQ to Entities sono un superset delle espressioni che possono essere utilizzate per eseguire una query [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]su.</span><span class="sxs-lookup"><span data-stu-id="4890c-109">The expressions that can be used in LINQ to Entities queries are a superset of the expressions that can be used to query the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="4890c-110">Le espressioni che fanno parte di query su [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] sono limitate alle operazioni supportate da `ObjectQuery<T>` e dall'origine dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="4890c-110">Expressions that are part of queries against the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] are limited to operations supported by `ObjectQuery<T>` and the underlying data source.</span></span>  
  
 <span data-ttu-id="4890c-111">Nell'esempio seguente il confronto nella clausola `Where` è un'espressione:</span><span class="sxs-lookup"><span data-stu-id="4890c-111">In the following example, the comparison in the `Where` clause is an expression:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
> <span data-ttu-id="4890c-112">Costrutti di linguaggio specifici, ad C# `unchecked`esempio, non hanno significato in LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="4890c-112">Specific language constructs, such as C# `unchecked`, have no meaning in LINQ to Entities.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4890c-113">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="4890c-113">In This Section</span></span>  
 [<span data-ttu-id="4890c-114">Espressioni costanti</span><span class="sxs-lookup"><span data-stu-id="4890c-114">Constant Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constant-expressions.md)  
  
 [<span data-ttu-id="4890c-115">Espressioni di confronto</span><span class="sxs-lookup"><span data-stu-id="4890c-115">Comparison Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-expressions.md)  
  
 [<span data-ttu-id="4890c-116">Confronti Null</span><span class="sxs-lookup"><span data-stu-id="4890c-116">Null Comparisons</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/null-comparisons.md)  
  
 [<span data-ttu-id="4890c-117">Espressioni di inizializzazione</span><span class="sxs-lookup"><span data-stu-id="4890c-117">Initialization Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/initialization-expressions.md)  
  
 [<span data-ttu-id="4890c-118">Relazioni, proprietà di navigazione e chiavi esterne</span><span class="sxs-lookup"><span data-stu-id="4890c-118">Relationships, navigation properties and foreign keys</span></span>](/ef/ef6/fundamentals/relationships)  
  
## <a name="see-also"></a><span data-ttu-id="4890c-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4890c-119">See also</span></span>

- [<span data-ttu-id="4890c-120">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="4890c-120">ADO.NET Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/index.md)
