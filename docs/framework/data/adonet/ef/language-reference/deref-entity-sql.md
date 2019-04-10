---
title: DEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4c78e833-b260-453d-9bf4-eb39857dd0fa
ms.openlocfilehash: 1ba562ba6542e6ab0d62f1f8348434ae4f4c9b13
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59305182"
---
# <a name="deref-entity-sql"></a><span data-ttu-id="7d21d-102">DEREF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="7d21d-102">DEREF (Entity SQL)</span></span>
<span data-ttu-id="7d21d-103">Consente di dereferenziare un valore di riferimento e restituisce il risultato di tale operazione.</span><span class="sxs-lookup"><span data-stu-id="7d21d-103">Dereferences a reference value and produces the result of that dereference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d21d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7d21d-104">Syntax</span></span>  
  
```  
SELECT DEREF ( o.expression ) from Table as o;  
```  
  
## <a name="arguments"></a><span data-ttu-id="7d21d-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="7d21d-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="7d21d-106">Qualsiasi espressione di query valida che restituisce una raccolta.</span><span class="sxs-lookup"><span data-stu-id="7d21d-106">Any valid query expression that returns a collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d21d-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7d21d-107">Return Value</span></span>  
 <span data-ttu-id="7d21d-108">Valore dell'entità di cui viene risolto il riferimento.</span><span class="sxs-lookup"><span data-stu-id="7d21d-108">The value of the entity that is referenced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d21d-109">Note</span><span class="sxs-lookup"><span data-stu-id="7d21d-109">Remarks</span></span>  
 <span data-ttu-id="7d21d-110">L'operatore DEREF consente di dereferenziare un valore di riferimento e restituisce il risultato di tale operazione.</span><span class="sxs-lookup"><span data-stu-id="7d21d-110">The DEREF operator dereferences a reference value and produces the result of that dereference.</span></span> <span data-ttu-id="7d21d-111">Ad esempio, se `r` è un riferimento di tipo ref\<T >, `Deref(r)` è un'espressione di tipo `T` che restituisce l'entità fa riferimento `r`.</span><span class="sxs-lookup"><span data-stu-id="7d21d-111">For example, if `r` is a reference of type ref\<T>, `Deref(r)` is an expression of type `T` that yields the entity referenced by `r`.</span></span> <span data-ttu-id="7d21d-112">Se il valore di riferimento è Null o è inesatto, ovvero la destinazione del riferimento non esiste, il risultato dell'operatore DEREF è Null.</span><span class="sxs-lookup"><span data-stu-id="7d21d-112">If the reference value is null, or is dangling (that is, the target of the reference does not exist), the result of the DEREF operator is null.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d21d-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="7d21d-113">Example</span></span>  
 <span data-ttu-id="7d21d-114">Nella query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguente viene usato l'operatore DEREF per dereferenziare un valore di riferimento e viene restituito il risultato di tale operazione.</span><span class="sxs-lookup"><span data-stu-id="7d21d-114">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the DEREF operator to dereference a reference value and produce the result of that dereference.</span></span> <span data-ttu-id="7d21d-115">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="7d21d-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="7d21d-116">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7d21d-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="7d21d-117">Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="7d21d-117">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="7d21d-118">Passare la query seguente come argomento al metodo ExecutePrimitiveTypeQuery:</span><span class="sxs-lookup"><span data-stu-id="7d21d-118">Pass the following query as an argument to the ExecutePrimitiveTypeQuery method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#DEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#deref)]  
  
## <a name="see-also"></a><span data-ttu-id="7d21d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d21d-119">See also</span></span>

- [<span data-ttu-id="7d21d-120">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="7d21d-120">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="7d21d-121">REF</span><span class="sxs-lookup"><span data-stu-id="7d21d-121">REF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)
- [<span data-ttu-id="7d21d-122">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="7d21d-122">CREATEREF</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)
- [<span data-ttu-id="7d21d-123">KEY</span><span class="sxs-lookup"><span data-stu-id="7d21d-123">KEY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)
- [<span data-ttu-id="7d21d-124">Tipi strutturati nullable</span><span class="sxs-lookup"><span data-stu-id="7d21d-124">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
