---
title: '! (NOT) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
ms.openlocfilehash: 7755219c5238f78e59332c508643fe2ae1f5096f
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319523"
---
# <a name="-not-entity-sql"></a><span data-ttu-id="86680-103">!</span><span class="sxs-lookup"><span data-stu-id="86680-103">!</span></span> <span data-ttu-id="86680-104">(NOT) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="86680-104">(NOT) (Entity SQL)</span></span>
<span data-ttu-id="86680-105">Nega un'espressione `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="86680-105">Negates a `Boolean` expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86680-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="86680-106">Syntax</span></span>  
  
```sql  
NOT boolean_expression  
-- or  
! boolean_expression  
``` 
  
## <a name="arguments"></a><span data-ttu-id="86680-107">argomenti</span><span class="sxs-lookup"><span data-stu-id="86680-107">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="86680-108">Qualsiasi espressione valida che restituisce un valore Boolean.</span><span class="sxs-lookup"><span data-stu-id="86680-108">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86680-109">Note</span><span class="sxs-lookup"><span data-stu-id="86680-109">Remarks</span></span>  
 <span data-ttu-id="86680-110">Il punto esclamativo (!) ha la stessa funzionalità dell'operatore NOT.</span><span class="sxs-lookup"><span data-stu-id="86680-110">The exclamation point (!) has the same functionality as the NOT operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86680-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="86680-111">Example</span></span>  
 <span data-ttu-id="86680-112">Nella query Entity SQL seguente viene usato l'operatore NOT per negare un'espressione `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="86680-112">The following Entity SQL query uses the NOT operator to negates a `Boolean` expression.</span></span> <span data-ttu-id="86680-113">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="86680-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="86680-114">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="86680-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="86680-115">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="86680-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="86680-116">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="86680-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NOT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#not)]  
  
## <a name="see-also"></a><span data-ttu-id="86680-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86680-117">See also</span></span>

- [<span data-ttu-id="86680-118">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="86680-118">Entity SQL Reference</span></span>](entity-sql-reference.md)
