---
title: ANYELEMENT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 475a9ad6-8c8d-4f49-9970-af273e5360f1
ms.openlocfilehash: 11d1dd4b09ff07519f3435d313de72c5b9a3edf4
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="anyelement-entity-sql"></a><span data-ttu-id="9363d-102">ANYELEMENT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="9363d-102">ANYELEMENT (Entity SQL)</span></span>
<span data-ttu-id="9363d-103">Estrae un elemento da una raccolta multivalore.</span><span class="sxs-lookup"><span data-stu-id="9363d-103">Extracts an element from a multivalued collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9363d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9363d-104">Syntax</span></span>  
  
```  
ANYELEMENT ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="9363d-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="9363d-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="9363d-106">Qualsiasi espressione di query valida che restituisce una raccolta da cui estrarre un elemento.</span><span class="sxs-lookup"><span data-stu-id="9363d-106">Any valid query expression that returns a collection to extract an element from.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9363d-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9363d-107">Return Value</span></span>  
 <span data-ttu-id="9363d-108">Singolo elemento nella raccolta o elemento arbitrario se nella raccolta ne è presente più di uno; se la raccolta è vuota, restituisce `null`.</span><span class="sxs-lookup"><span data-stu-id="9363d-108">A single element in the collection or an arbitrary element if the collection has more than one; if the collection is empty, returns `null`.</span></span> <span data-ttu-id="9363d-109">Se `collection` è una raccolta di tipo `Collection<T>`, quindi `ANYELEMENT(collection)` è un'espressione valida che produce un'istanza di tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="9363d-109">If `collection` is a collection of type `Collection<T>`, then `ANYELEMENT(collection)` is a valid expression that yields an instance of type `T`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9363d-110">Note</span><span class="sxs-lookup"><span data-stu-id="9363d-110">Remarks</span></span>  
 <span data-ttu-id="9363d-111">ANYELEMENT estrae un elemento arbitrario da una raccolta multivalore.</span><span class="sxs-lookup"><span data-stu-id="9363d-111">ANYELEMENT extracts an arbitrary element from a multivalued collection.</span></span> <span data-ttu-id="9363d-112">Nell'esempio seguente viene ad esempio eseguito un tentativo di estrarre un elemento singleton dal set `Customers`.</span><span class="sxs-lookup"><span data-stu-id="9363d-112">For example, the following example attempts to extract a singleton element from the set `Customers`.</span></span>  
  
```  
ANYELEMENT(Customers)  
```  
  
## <a name="example"></a><span data-ttu-id="9363d-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="9363d-113">Example</span></span>  
 <span data-ttu-id="9363d-114">Nella query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguente viene usato l'operatore ANYELEMENT per estrarre un elemento da una raccolta multivalore.</span><span class="sxs-lookup"><span data-stu-id="9363d-114">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the ANYELEMENT operator to extract an element from a multivalued collection.</span></span> <span data-ttu-id="9363d-115">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="9363d-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="9363d-116">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9363d-116">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="9363d-117">Seguire la procedura indicata in [Procedura: eseguire una query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="9363d-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="9363d-118">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="9363d-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ANYELEMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#anyelement)]  
  
## <a name="see-also"></a><span data-ttu-id="9363d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9363d-119">See Also</span></span>  
 [<span data-ttu-id="9363d-120">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="9363d-120">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="9363d-121">Tipi strutturati nullable</span><span class="sxs-lookup"><span data-stu-id="9363d-121">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
