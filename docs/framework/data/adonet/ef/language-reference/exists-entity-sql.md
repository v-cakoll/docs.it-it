---
title: EXISTS (Entity SQL)
ms.date: 03/30/2017
ms.assetid: d28ead43-4afb-4bdc-af64-efd2e05005d7
ms.openlocfilehash: 20e18bf536f2b89eca9515b3c5dca7ca7fbd6fe5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250983"
---
# <a name="exists-entity-sql"></a><span data-ttu-id="f9733-102">EXISTS (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f9733-102">EXISTS (Entity SQL)</span></span>
<span data-ttu-id="f9733-103">Determina se una raccolta è vuota.</span><span class="sxs-lookup"><span data-stu-id="f9733-103">Determines if a collection is empty.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9733-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f9733-104">Syntax</span></span>  
  
```  
[NOT] EXISTS ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="f9733-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="f9733-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="f9733-106">Qualsiasi espressione valida che restituisce una raccolta.</span><span class="sxs-lookup"><span data-stu-id="f9733-106">Any valid expression that returns a collection.</span></span>  
  
 <span data-ttu-id="f9733-107">NOT</span><span class="sxs-lookup"><span data-stu-id="f9733-107">NOT</span></span>  
 <span data-ttu-id="f9733-108">Specifica la negazione del risultato di EXISTS.</span><span class="sxs-lookup"><span data-stu-id="f9733-108">Specifies that the result of EXISTS be negated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f9733-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f9733-109">Return Value</span></span>  
 <span data-ttu-id="f9733-110">`true` se la raccolta non è vuota; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="f9733-110">`true` if the collection is not empty; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9733-111">Note</span><span class="sxs-lookup"><span data-stu-id="f9733-111">Remarks</span></span>  
 <span data-ttu-id="f9733-112">EXISTS è uno degli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9733-112">EXISTS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="f9733-113">Tutti gli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vengono valutati da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="f9733-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="f9733-114">Per informazioni sulla precedenza per [!INCLUDE[esql](../../../../../../includes/esql-md.md)] gli operatori sui set, vedere [except](except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="f9733-114">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9733-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="f9733-115">Example</span></span>  
 <span data-ttu-id="f9733-116">Nella query Entity SQL seguente viene usato l'operatore EXISTS per determinare se la raccolta è vuota.</span><span class="sxs-lookup"><span data-stu-id="f9733-116">The following Entity SQL query uses the EXISTS operator to determine whether the collection is empty.</span></span> <span data-ttu-id="f9733-117">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="f9733-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="f9733-118">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9733-118">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="f9733-119">Attenersi alla procedura descritta [in procedura: Eseguire una query che restituisce i risultati](../how-to-execute-a-query-that-returns-structuraltype-results.md)di StructuralType.</span><span class="sxs-lookup"><span data-stu-id="f9733-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="f9733-120">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="f9733-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EXISTS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#exists)]  
  
## <a name="see-also"></a><span data-ttu-id="f9733-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9733-121">See also</span></span>

- [<span data-ttu-id="f9733-122">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="f9733-122">Entity SQL Reference</span></span>](entity-sql-reference.md)
