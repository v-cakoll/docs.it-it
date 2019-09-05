---
title: '&amp;&amp; (AND) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: 02e404b73e5a9a9c3963e2d2b58ab7592afabc13
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251319"
---
# <a name="ampamp-and-entity-sql"></a><span data-ttu-id="d8507-102">&amp;&amp; (AND) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d8507-102">&amp;&amp; (AND) (Entity SQL)</span></span>
<span data-ttu-id="d8507-103">Restituisce `true` se entrambe le espressioni sono `true`; in caso contrario, restituisce `false` o `NULL`.</span><span class="sxs-lookup"><span data-stu-id="d8507-103">Returns `true` if both expressions are `true`; otherwise, `false` or `NULL`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8507-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d8507-104">Syntax</span></span>  
  
```  
boolean_expression AND boolean_expression  
or  
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="d8507-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d8507-105">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="d8507-106">Qualsiasi espressione valida che restituisce un valore Boolean.</span><span class="sxs-lookup"><span data-stu-id="d8507-106">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8507-107">Note</span><span class="sxs-lookup"><span data-stu-id="d8507-107">Remarks</span></span>  
 <span data-ttu-id="d8507-108">L'utilizzo di due caratteri di e commerciale (&&) ha la stessa funzionalità dell'operatore AND.</span><span class="sxs-lookup"><span data-stu-id="d8507-108">Double ampersands (&&) have the same functionality as the AND operator.</span></span>  
  
 <span data-ttu-id="d8507-109">Nella tabella seguente sono inclusi i possibili valori di input e i tipi restituiti.</span><span class="sxs-lookup"><span data-stu-id="d8507-109">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="d8507-110">TRUE</span><span class="sxs-lookup"><span data-stu-id="d8507-110">TRUE</span></span>|<span data-ttu-id="d8507-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="d8507-111">FALSE</span></span>|<span data-ttu-id="d8507-112">NULL</span><span class="sxs-lookup"><span data-stu-id="d8507-112">NULL</span></span>|  
|`FALSE`|<span data-ttu-id="d8507-113">FALSE</span><span class="sxs-lookup"><span data-stu-id="d8507-113">FALSE</span></span>|<span data-ttu-id="d8507-114">FALSE</span><span class="sxs-lookup"><span data-stu-id="d8507-114">FALSE</span></span>|<span data-ttu-id="d8507-115">FALSE</span><span class="sxs-lookup"><span data-stu-id="d8507-115">FALSE</span></span>|  
|`NULL`|<span data-ttu-id="d8507-116">NULL</span><span class="sxs-lookup"><span data-stu-id="d8507-116">NULL</span></span>|<span data-ttu-id="d8507-117">false</span><span class="sxs-lookup"><span data-stu-id="d8507-117">FALSE</span></span>|<span data-ttu-id="d8507-118">NULL</span><span class="sxs-lookup"><span data-stu-id="d8507-118">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d8507-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="d8507-119">Example</span></span>  
 <span data-ttu-id="d8507-120">Nella query Entity SQL seguente viene illustrato come usare l'operatore AND.</span><span class="sxs-lookup"><span data-stu-id="d8507-120">The following Entity SQL query demonstrates how to use the AND operator.</span></span> <span data-ttu-id="d8507-121">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="d8507-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="d8507-122">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d8507-122">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="d8507-123">Attenersi alla procedura descritta [in procedura: Eseguire una query che restituisce i risultati](../how-to-execute-a-query-that-returns-structuraltype-results.md)di StructuralType.</span><span class="sxs-lookup"><span data-stu-id="d8507-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="d8507-124">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="d8507-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a><span data-ttu-id="d8507-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8507-125">See also</span></span>

- [<span data-ttu-id="d8507-126">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d8507-126">Entity SQL Reference</span></span>](entity-sql-reference.md)
