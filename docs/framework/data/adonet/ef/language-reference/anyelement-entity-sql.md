---
title: ANYELEMENT (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 475a9ad6-8c8d-4f49-9970-af273e5360f1
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: de08e590bcc7b2380f2edda0ebc918d7ce328f4c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="anyelement-entity-sql"></a><span data-ttu-id="9a466-102">ANYELEMENT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="9a466-102">ANYELEMENT (Entity SQL)</span></span>
<span data-ttu-id="9a466-103">Estrae un elemento da una raccolta multivalore.</span><span class="sxs-lookup"><span data-stu-id="9a466-103">Extracts an element from a multivalued collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a466-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a466-104">Syntax</span></span>  
  
```  
ANYELEMENT ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="9a466-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="9a466-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="9a466-106">Qualsiasi espressione di query valida che restituisce una raccolta da cui estrarre un elemento.</span><span class="sxs-lookup"><span data-stu-id="9a466-106">Any valid query expression that returns a collection to extract an element from.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a466-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9a466-107">Return Value</span></span>  
 <span data-ttu-id="9a466-108">Singolo elemento nella raccolta o elemento arbitrario se nella raccolta ne è presente più di uno; se la raccolta è vuota, restituisce `null`.</span><span class="sxs-lookup"><span data-stu-id="9a466-108">A single element in the collection or an arbitrary element if the collection has more than one; if the collection is empty, returns `null`.</span></span> <span data-ttu-id="9a466-109">Se `collection` è una raccolta di tipo `Collection<T>`, quindi `ANYELEMENT(collection)` è un'espressione valida che produce un'istanza di tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="9a466-109">If `collection` is a collection of type `Collection<T>`, then `ANYELEMENT(collection)` is a valid expression that yields an instance of type `T`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a466-110">Note</span><span class="sxs-lookup"><span data-stu-id="9a466-110">Remarks</span></span>  
 <span data-ttu-id="9a466-111">ANYELEMENT estrae un elemento arbitrario da una raccolta multivalore.</span><span class="sxs-lookup"><span data-stu-id="9a466-111">ANYELEMENT extracts an arbitrary element from a multivalued collection.</span></span> <span data-ttu-id="9a466-112">Nell'esempio seguente viene ad esempio eseguito un tentativo di estrarre un elemento singleton dal set `Customers`.</span><span class="sxs-lookup"><span data-stu-id="9a466-112">For example, the following example attempts to extract a singleton element from the set `Customers`.</span></span>  
  
```  
ANYELEMENT(Customers)  
```  
  
## <a name="example"></a><span data-ttu-id="9a466-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="9a466-113">Example</span></span>  
 <span data-ttu-id="9a466-114">Nella query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguente viene usato l'operatore ANYELEMENT per estrarre un elemento da una raccolta multivalore.</span><span class="sxs-lookup"><span data-stu-id="9a466-114">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the ANYELEMENT operator to extract an element from a multivalued collection.</span></span> <span data-ttu-id="9a466-115">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="9a466-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="9a466-116">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a466-116">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="9a466-117">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="9a466-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="9a466-118">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="9a466-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ANYELEMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#anyelement)]  
  
## <a name="see-also"></a><span data-ttu-id="9a466-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a466-119">See Also</span></span>  
 [<span data-ttu-id="9a466-120">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="9a466-120">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="9a466-121">Tipi strutturati nullable</span><span class="sxs-lookup"><span data-stu-id="9a466-121">Nullable Structured Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)
