---
title: Espressioni in query di LINQ to Entities
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d70b502f-6a15-4120-b4fe-500b173ad9cc
ms.openlocfilehash: e625ac3968542c65e737093c0ac292de4c2ffa37
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854467"
---
# <a name="expressions-in-linq-to-entities-queries"></a><span data-ttu-id="4159f-102">Espressioni in query di LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="4159f-102">Expressions in LINQ to Entities Queries</span></span>
<span data-ttu-id="4159f-103">Un'espressione è un frammento di codice che può restituire un singolo valore, oggetto, metodo o spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="4159f-103">An expression is a fragment of code that can be evaluated to a single value, object, method, or namespace.</span></span> <span data-ttu-id="4159f-104">Le espressioni possono contenere un valore letterale, una chiamata al metodo, un operatore e i relativi operandi oppure un nome semplice,</span><span class="sxs-lookup"><span data-stu-id="4159f-104">Expressions can contain a literal value, a method call, an operator and its operands, or a simple name.</span></span> <span data-ttu-id="4159f-105">ad esempio il nome di una variabile, un membro di un tipo, un parametro di un metodo, uno spazio dei nomi o un tipo.</span><span class="sxs-lookup"><span data-stu-id="4159f-105">Simple names can be the name of a variable, type member, method parameter, namespace or type.</span></span> <span data-ttu-id="4159f-106">Le espressioni possono usare operatori che a loro volta usano altre espressioni come parametri oppure chiamate a metodi i cui parametri sono a loro volta altre chiamate a metodi.</span><span class="sxs-lookup"><span data-stu-id="4159f-106">Expressions can use operators that in turn use other expressions as parameters, or method calls whose parameters are in turn other method calls.</span></span> <span data-ttu-id="4159f-107">Le espressioni possono pertanto essere da semplici a molto complesse.</span><span class="sxs-lookup"><span data-stu-id="4159f-107">Therefore, expressions can range from simple to very complex.</span></span>  
  
 <span data-ttu-id="4159f-108">Nelle query LINQ to Entities, le espressioni possono contenere qualsiasi elemento consentito dai tipi all' <xref:System.Linq.Expressions> interno dello spazio dei nomi, incluse le espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="4159f-108">In LINQ to Entities queries, expressions can contain anything allowed by the types within the <xref:System.Linq.Expressions> namespace, including lambda expressions.</span></span> <span data-ttu-id="4159f-109">Le espressioni che possono essere utilizzate nelle query LINQ to Entities sono un superset delle espressioni che possono essere utilizzate per eseguire query sul Entity Framework. le espressioni che fanno parte di query sul Entity Framework sono limitate alle operazioni supportate da `ObjectQuery<T>` e origine dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="4159f-109">The expressions that can be used in LINQ to Entities queries are a superset of the expressions that can be used to query the Entity Framework.Expressions that are part of queries against the Entity Framework are limited to operations supported by `ObjectQuery<T>` and the underlying data source.</span></span>  
  
 <span data-ttu-id="4159f-110">Nell'esempio seguente il confronto nella clausola `Where` è un'espressione:</span><span class="sxs-lookup"><span data-stu-id="4159f-110">In the following example, the comparison in the `Where` clause is an expression:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
> <span data-ttu-id="4159f-111">Costrutti di linguaggio specifici, ad C# `unchecked`esempio, non hanno significato in LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="4159f-111">Specific language constructs, such as C# `unchecked`, have no meaning in LINQ to Entities.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4159f-112">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="4159f-112">In This Section</span></span>  
 [<span data-ttu-id="4159f-113">Espressioni costanti</span><span class="sxs-lookup"><span data-stu-id="4159f-113">Constant Expressions</span></span>](constant-expressions.md)  
  
 [<span data-ttu-id="4159f-114">Espressioni di confronto</span><span class="sxs-lookup"><span data-stu-id="4159f-114">Comparison Expressions</span></span>](comparison-expressions.md)  
  
 [<span data-ttu-id="4159f-115">Confronti Null</span><span class="sxs-lookup"><span data-stu-id="4159f-115">Null Comparisons</span></span>](null-comparisons.md)  
  
 [<span data-ttu-id="4159f-116">Espressioni di inizializzazione</span><span class="sxs-lookup"><span data-stu-id="4159f-116">Initialization Expressions</span></span>](initialization-expressions.md)  
  
 [<span data-ttu-id="4159f-117">Relazioni, proprietà di navigazione e chiavi esterne</span><span class="sxs-lookup"><span data-stu-id="4159f-117">Relationships, navigation properties and foreign keys</span></span>](/ef/ef6/fundamentals/relationships)  
  
## <a name="see-also"></a><span data-ttu-id="4159f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4159f-118">See also</span></span>

- [<span data-ttu-id="4159f-119">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="4159f-119">ADO.NET Entity Framework</span></span>](../index.md)
