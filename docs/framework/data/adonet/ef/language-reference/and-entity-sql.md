---
title: '&amp;&amp;(E) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: eccad616de287a39c42e986cea84dc22feec7f70
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150511"
---
# <a name="ampamp-and-entity-sql"></a><span data-ttu-id="e97c5-102">&amp;&amp;(E) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e97c5-102">&amp;&amp; (AND) (Entity SQL)</span></span>
<span data-ttu-id="e97c5-103">Restituisce `true` se entrambe le espressioni sono `true`; in caso contrario, restituisce `false` o `NULL`.</span><span class="sxs-lookup"><span data-stu-id="e97c5-103">Returns `true` if both expressions are `true`; otherwise, `false` or `NULL`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e97c5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e97c5-104">Syntax</span></span>  
  
```csharp  
boolean_expression AND boolean_expression
```

<span data-ttu-id="e97c5-105">o</span><span class="sxs-lookup"><span data-stu-id="e97c5-105">or</span></span>  

```csharp
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="e97c5-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="e97c5-106">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="e97c5-107">Qualsiasi espressione valida che restituisce un valore Boolean.</span><span class="sxs-lookup"><span data-stu-id="e97c5-107">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e97c5-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e97c5-108">Remarks</span></span>  
 <span data-ttu-id="e97c5-109">L'utilizzo di due caratteri di e commerciale (&&) ha la stessa funzionalità dell'operatore AND.</span><span class="sxs-lookup"><span data-stu-id="e97c5-109">Double ampersands (&&) have the same functionality as the AND operator.</span></span>  
  
 <span data-ttu-id="e97c5-110">Nella tabella seguente sono inclusi i possibili valori di input e i tipi restituiti.</span><span class="sxs-lookup"><span data-stu-id="e97c5-110">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="e97c5-111">TRUE</span><span class="sxs-lookup"><span data-stu-id="e97c5-111">TRUE</span></span>|<span data-ttu-id="e97c5-112">FALSE</span><span class="sxs-lookup"><span data-stu-id="e97c5-112">FALSE</span></span>|<span data-ttu-id="e97c5-113">NULL</span><span class="sxs-lookup"><span data-stu-id="e97c5-113">NULL</span></span>|  
|`FALSE`|<span data-ttu-id="e97c5-114">FALSE</span><span class="sxs-lookup"><span data-stu-id="e97c5-114">FALSE</span></span>|<span data-ttu-id="e97c5-115">FALSE</span><span class="sxs-lookup"><span data-stu-id="e97c5-115">FALSE</span></span>|<span data-ttu-id="e97c5-116">FALSE</span><span class="sxs-lookup"><span data-stu-id="e97c5-116">FALSE</span></span>|  
|`NULL`|<span data-ttu-id="e97c5-117">NULL</span><span class="sxs-lookup"><span data-stu-id="e97c5-117">NULL</span></span>|<span data-ttu-id="e97c5-118">FALSE</span><span class="sxs-lookup"><span data-stu-id="e97c5-118">FALSE</span></span>|<span data-ttu-id="e97c5-119">NULL</span><span class="sxs-lookup"><span data-stu-id="e97c5-119">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e97c5-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="e97c5-120">Example</span></span>  
 <span data-ttu-id="e97c5-121">Nella query Entity SQL seguente viene illustrato come usare l'operatore AND.</span><span class="sxs-lookup"><span data-stu-id="e97c5-121">The following Entity SQL query demonstrates how to use the AND operator.</span></span> <span data-ttu-id="e97c5-122">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="e97c5-122">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="e97c5-123">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e97c5-123">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="e97c5-124">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="e97c5-124">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="e97c5-125">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="e97c5-125">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a><span data-ttu-id="e97c5-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e97c5-126">See also</span></span>

- [<span data-ttu-id="e97c5-127">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e97c5-127">Entity SQL Reference</span></span>](entity-sql-reference.md)
