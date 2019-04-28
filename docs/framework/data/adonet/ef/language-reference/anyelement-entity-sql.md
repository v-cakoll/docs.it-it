---
title: ANYELEMENT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 475a9ad6-8c8d-4f49-9970-af273e5360f1
ms.openlocfilehash: ff79417008b7807fbf206d4bcb65b4e5ea1cc576
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61606036"
---
# <a name="anyelement-entity-sql"></a><span data-ttu-id="6a3be-102">ANYELEMENT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6a3be-102">ANYELEMENT (Entity SQL)</span></span>
<span data-ttu-id="6a3be-103">Estrae un elemento da una raccolta multivalore.</span><span class="sxs-lookup"><span data-stu-id="6a3be-103">Extracts an element from a multivalued collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a3be-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6a3be-104">Syntax</span></span>  
  
```  
ANYELEMENT ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="6a3be-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="6a3be-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="6a3be-106">Qualsiasi espressione di query valida che restituisce una raccolta da cui estrarre un elemento.</span><span class="sxs-lookup"><span data-stu-id="6a3be-106">Any valid query expression that returns a collection to extract an element from.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6a3be-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6a3be-107">Return Value</span></span>  
 <span data-ttu-id="6a3be-108">Singolo elemento nella raccolta o elemento arbitrario se nella raccolta ne è presente più di uno; se la raccolta è vuota, restituisce `null`.</span><span class="sxs-lookup"><span data-stu-id="6a3be-108">A single element in the collection or an arbitrary element if the collection has more than one; if the collection is empty, returns `null`.</span></span> <span data-ttu-id="6a3be-109">Se `collection` è una raccolta di tipo `Collection<T>`, quindi `ANYELEMENT(collection)` è un'espressione valida che produce un'istanza del tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="6a3be-109">If `collection` is a collection of type `Collection<T>`, then `ANYELEMENT(collection)` is a valid expression that yields an instance of type `T`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a3be-110">Note</span><span class="sxs-lookup"><span data-stu-id="6a3be-110">Remarks</span></span>  
 <span data-ttu-id="6a3be-111">ANYELEMENT estrae un elemento arbitrario da una raccolta multivalore.</span><span class="sxs-lookup"><span data-stu-id="6a3be-111">ANYELEMENT extracts an arbitrary element from a multivalued collection.</span></span> <span data-ttu-id="6a3be-112">Nell'esempio seguente viene ad esempio eseguito un tentativo di estrarre un elemento singleton dal set `Customers`.</span><span class="sxs-lookup"><span data-stu-id="6a3be-112">For example, the following example attempts to extract a singleton element from the set `Customers`.</span></span>  
  
```  
ANYELEMENT(Customers)  
```  
  
## <a name="example"></a><span data-ttu-id="6a3be-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="6a3be-113">Example</span></span>  
 <span data-ttu-id="6a3be-114">Nella query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguente viene usato l'operatore ANYELEMENT per estrarre un elemento da una raccolta multivalore.</span><span class="sxs-lookup"><span data-stu-id="6a3be-114">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the ANYELEMENT operator to extract an element from a multivalued collection.</span></span> <span data-ttu-id="6a3be-115">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="6a3be-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="6a3be-116">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6a3be-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="6a3be-117">Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="6a3be-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="6a3be-118">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="6a3be-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ANYELEMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#anyelement)]  
  
## <a name="see-also"></a><span data-ttu-id="6a3be-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a3be-119">See also</span></span>

- [<span data-ttu-id="6a3be-120">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="6a3be-120">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="6a3be-121">Tipi strutturati nullable</span><span class="sxs-lookup"><span data-stu-id="6a3be-121">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
