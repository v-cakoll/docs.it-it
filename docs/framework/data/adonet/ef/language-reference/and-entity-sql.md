---
title: '&amp;&amp; (AND) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: eab05f7454f8ebc88ed29030503bfa96d0c70756
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59308432"
---
# <a name="ampamp-and-entity-sql"></a><span data-ttu-id="dcd60-102">&amp;&amp; (AND) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="dcd60-102">&amp;&amp; (AND) (Entity SQL)</span></span>
<span data-ttu-id="dcd60-103">Restituisce `true` se entrambe le espressioni sono `true`; in caso contrario, restituisce `false` o `NULL`.</span><span class="sxs-lookup"><span data-stu-id="dcd60-103">Returns `true` if both expressions are `true`; otherwise, `false` or `NULL`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcd60-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dcd60-104">Syntax</span></span>  
  
```  
boolean_expression AND boolean_expression  
or  
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="dcd60-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="dcd60-105">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="dcd60-106">Qualsiasi espressione valida che restituisce un valore Boolean.</span><span class="sxs-lookup"><span data-stu-id="dcd60-106">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dcd60-107">Note</span><span class="sxs-lookup"><span data-stu-id="dcd60-107">Remarks</span></span>  
 <span data-ttu-id="dcd60-108">L'utilizzo di due caratteri di e commerciale (&&) ha la stessa funzionalità dell'operatore AND.</span><span class="sxs-lookup"><span data-stu-id="dcd60-108">Double ampersands (&&) have the same functionality as the AND operator.</span></span>  
  
 <span data-ttu-id="dcd60-109">Nella tabella seguente sono inclusi i possibili valori di input e i tipi restituiti.</span><span class="sxs-lookup"><span data-stu-id="dcd60-109">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="dcd60-110">TRUE</span><span class="sxs-lookup"><span data-stu-id="dcd60-110">TRUE</span></span>|<span data-ttu-id="dcd60-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="dcd60-111">FALSE</span></span>|<span data-ttu-id="dcd60-112">NULL</span><span class="sxs-lookup"><span data-stu-id="dcd60-112">NULL</span></span>|  
|`FALSE`|<span data-ttu-id="dcd60-113">FALSE</span><span class="sxs-lookup"><span data-stu-id="dcd60-113">FALSE</span></span>|<span data-ttu-id="dcd60-114">FALSE</span><span class="sxs-lookup"><span data-stu-id="dcd60-114">FALSE</span></span>|<span data-ttu-id="dcd60-115">FALSE</span><span class="sxs-lookup"><span data-stu-id="dcd60-115">FALSE</span></span>|  
|`NULL`|<span data-ttu-id="dcd60-116">NULL</span><span class="sxs-lookup"><span data-stu-id="dcd60-116">NULL</span></span>|<span data-ttu-id="dcd60-117">false</span><span class="sxs-lookup"><span data-stu-id="dcd60-117">FALSE</span></span>|<span data-ttu-id="dcd60-118">NULL</span><span class="sxs-lookup"><span data-stu-id="dcd60-118">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="dcd60-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="dcd60-119">Example</span></span>  
 <span data-ttu-id="dcd60-120">Nella query Entity SQL seguente viene illustrato come usare l'operatore AND.</span><span class="sxs-lookup"><span data-stu-id="dcd60-120">The following Entity SQL query demonstrates how to use the AND operator.</span></span> <span data-ttu-id="dcd60-121">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="dcd60-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="dcd60-122">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dcd60-122">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="dcd60-123">Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="dcd60-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="dcd60-124">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="dcd60-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a><span data-ttu-id="dcd60-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dcd60-125">See also</span></span>

- [<span data-ttu-id="dcd60-126">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="dcd60-126">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
