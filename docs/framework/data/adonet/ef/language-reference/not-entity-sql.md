---
title: '! (NOT) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
ms.openlocfilehash: 0b69d4cb64adc1f9232631d50ec42af0d1ba47e3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150129"
---
# <a name="-not-entity-sql"></a><span data-ttu-id="906f0-103">!</span><span class="sxs-lookup"><span data-stu-id="906f0-103">!</span></span> <span data-ttu-id="906f0-104">(NOT) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="906f0-104">(NOT) (Entity SQL)</span></span>
<span data-ttu-id="906f0-105">Nega un'espressione `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="906f0-105">Negates a `Boolean` expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="906f0-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="906f0-106">Syntax</span></span>  
  
```sql  
NOT boolean_expression  
-- or  
! boolean_expression  
```
  
## <a name="arguments"></a><span data-ttu-id="906f0-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="906f0-107">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="906f0-108">Qualsiasi espressione valida che restituisce un valore Boolean.</span><span class="sxs-lookup"><span data-stu-id="906f0-108">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="906f0-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="906f0-109">Remarks</span></span>  
 <span data-ttu-id="906f0-110">Il punto esclamativo (!) ha la stessa funzionalità dell'operatore NOT.</span><span class="sxs-lookup"><span data-stu-id="906f0-110">The exclamation point (!) has the same functionality as the NOT operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="906f0-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="906f0-111">Example</span></span>  
 <span data-ttu-id="906f0-112">Nella query Entity SQL seguente viene usato l'operatore NOT per negare un'espressione `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="906f0-112">The following Entity SQL query uses the NOT operator to negates a `Boolean` expression.</span></span> <span data-ttu-id="906f0-113">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="906f0-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="906f0-114">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="906f0-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="906f0-115">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="906f0-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="906f0-116">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="906f0-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NOT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#not)]  
  
## <a name="see-also"></a><span data-ttu-id="906f0-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="906f0-117">See also</span></span>

- [<span data-ttu-id="906f0-118">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="906f0-118">Entity SQL Reference</span></span>](entity-sql-reference.md)
