---
title: ANYELEMENT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 475a9ad6-8c8d-4f49-9970-af273e5360f1
ms.openlocfilehash: c0f7686f7ff3f6458637b51e29ecafe0c0ccfbc4
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040315"
---
# <a name="anyelement-entity-sql"></a><span data-ttu-id="26cc9-102">ANYELEMENT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="26cc9-102">ANYELEMENT (Entity SQL)</span></span>
<span data-ttu-id="26cc9-103">Estrae un elemento da una raccolta multivalore.</span><span class="sxs-lookup"><span data-stu-id="26cc9-103">Extracts an element from a multivalued collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26cc9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="26cc9-104">Syntax</span></span>  
  
```csharp
ANYELEMENT ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="26cc9-105">argomenti</span><span class="sxs-lookup"><span data-stu-id="26cc9-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="26cc9-106">Qualsiasi espressione di query valida che restituisce una raccolta da cui estrarre un elemento.</span><span class="sxs-lookup"><span data-stu-id="26cc9-106">Any valid query expression that returns a collection to extract an element from.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="26cc9-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="26cc9-107">Return Value</span></span>  
 <span data-ttu-id="26cc9-108">Singolo elemento nella raccolta o elemento arbitrario se nella raccolta ne è presente più di uno; se la raccolta è vuota, restituisce `null`.</span><span class="sxs-lookup"><span data-stu-id="26cc9-108">A single element in the collection or an arbitrary element if the collection has more than one; if the collection is empty, returns `null`.</span></span> <span data-ttu-id="26cc9-109">Se `collection` è una raccolta di tipo `Collection<T>`, `ANYELEMENT(collection)` è un'espressione valida che produce un'istanza di tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="26cc9-109">If `collection` is a collection of type `Collection<T>`, then `ANYELEMENT(collection)` is a valid expression that yields an instance of type `T`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26cc9-110">Note</span><span class="sxs-lookup"><span data-stu-id="26cc9-110">Remarks</span></span>  
 <span data-ttu-id="26cc9-111">ANYELEMENT estrae un elemento arbitrario da una raccolta multivalore.</span><span class="sxs-lookup"><span data-stu-id="26cc9-111">ANYELEMENT extracts an arbitrary element from a multivalued collection.</span></span> <span data-ttu-id="26cc9-112">Nell'esempio seguente viene ad esempio eseguito un tentativo di estrarre un elemento singleton dal set `Customers`.</span><span class="sxs-lookup"><span data-stu-id="26cc9-112">For example, the following example attempts to extract a singleton element from the set `Customers`.</span></span>  
  
```csharp
ANYELEMENT(Customers)  
```  
  
## <a name="example"></a><span data-ttu-id="26cc9-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="26cc9-113">Example</span></span>  
 <span data-ttu-id="26cc9-114">Nella query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguente viene usato l'operatore ANYELEMENT per estrarre un elemento da una raccolta multivalore.</span><span class="sxs-lookup"><span data-stu-id="26cc9-114">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the ANYELEMENT operator to extract an element from a multivalued collection.</span></span> <span data-ttu-id="26cc9-115">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="26cc9-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="26cc9-116">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="26cc9-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="26cc9-117">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="26cc9-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="26cc9-118">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="26cc9-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ANYELEMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#anyelement)]  
  
## <a name="see-also"></a><span data-ttu-id="26cc9-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26cc9-119">See also</span></span>

- [<span data-ttu-id="26cc9-120">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="26cc9-120">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="26cc9-121">Tipi strutturati nullable</span><span class="sxs-lookup"><span data-stu-id="26cc9-121">Nullable Structured Types</span></span>](nullable-structured-types-entity-sql.md)
