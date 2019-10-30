---
title: '&amp;&amp; (e) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: be6e7120e6c19714f151aa38a8b9a1355de29d1a
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039957"
---
# <a name="ampamp-and-entity-sql"></a><span data-ttu-id="b3273-102">&amp;&amp; (e) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b3273-102">&amp;&amp; (AND) (Entity SQL)</span></span>
<span data-ttu-id="b3273-103">Restituisce `true` se entrambe le espressioni sono `true`; in caso contrario, restituisce `false` o `NULL`.</span><span class="sxs-lookup"><span data-stu-id="b3273-103">Returns `true` if both expressions are `true`; otherwise, `false` or `NULL`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3273-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b3273-104">Syntax</span></span>  
  
```csharp  
boolean_expression AND boolean_expression
```
 
<span data-ttu-id="b3273-105">Oppure</span><span class="sxs-lookup"><span data-stu-id="b3273-105">or</span></span>  

```csharp
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="b3273-106">argomenti</span><span class="sxs-lookup"><span data-stu-id="b3273-106">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="b3273-107">Qualsiasi espressione valida che restituisce un valore Boolean.</span><span class="sxs-lookup"><span data-stu-id="b3273-107">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3273-108">Note</span><span class="sxs-lookup"><span data-stu-id="b3273-108">Remarks</span></span>  
 <span data-ttu-id="b3273-109">L'utilizzo di due caratteri di e commerciale (&&) ha la stessa funzionalità dell'operatore AND.</span><span class="sxs-lookup"><span data-stu-id="b3273-109">Double ampersands (&&) have the same functionality as the AND operator.</span></span>  
  
 <span data-ttu-id="b3273-110">Nella tabella seguente sono inclusi i possibili valori di input e i tipi restituiti.</span><span class="sxs-lookup"><span data-stu-id="b3273-110">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="b3273-111">true</span><span class="sxs-lookup"><span data-stu-id="b3273-111">TRUE</span></span>|<span data-ttu-id="b3273-112">false</span><span class="sxs-lookup"><span data-stu-id="b3273-112">FALSE</span></span>|<span data-ttu-id="b3273-113">NULL</span><span class="sxs-lookup"><span data-stu-id="b3273-113">NULL</span></span>|  
|`FALSE`|<span data-ttu-id="b3273-114">false</span><span class="sxs-lookup"><span data-stu-id="b3273-114">FALSE</span></span>|<span data-ttu-id="b3273-115">false</span><span class="sxs-lookup"><span data-stu-id="b3273-115">FALSE</span></span>|<span data-ttu-id="b3273-116">false</span><span class="sxs-lookup"><span data-stu-id="b3273-116">FALSE</span></span>|  
|`NULL`|<span data-ttu-id="b3273-117">NULL</span><span class="sxs-lookup"><span data-stu-id="b3273-117">NULL</span></span>|<span data-ttu-id="b3273-118">false</span><span class="sxs-lookup"><span data-stu-id="b3273-118">FALSE</span></span>|<span data-ttu-id="b3273-119">NULL</span><span class="sxs-lookup"><span data-stu-id="b3273-119">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b3273-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="b3273-120">Example</span></span>  
 <span data-ttu-id="b3273-121">Nella query Entity SQL seguente viene illustrato come usare l'operatore AND.</span><span class="sxs-lookup"><span data-stu-id="b3273-121">The following Entity SQL query demonstrates how to use the AND operator.</span></span> <span data-ttu-id="b3273-122">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="b3273-122">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="b3273-123">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b3273-123">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="b3273-124">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="b3273-124">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="b3273-125">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="b3273-125">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a><span data-ttu-id="b3273-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3273-126">See also</span></span>

- [<span data-ttu-id="b3273-127">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="b3273-127">Entity SQL Reference</span></span>](entity-sql-reference.md)
