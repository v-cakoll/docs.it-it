---
title: EXISTS (Entity SQL)
ms.date: 03/30/2017
ms.assetid: d28ead43-4afb-4bdc-af64-efd2e05005d7
ms.openlocfilehash: 76be542c64f75f27d126d7dbb6bde2baea8f6016
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078239"
---
# <a name="exists-entity-sql"></a><span data-ttu-id="4a87e-102">EXISTS (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="4a87e-102">EXISTS (Entity SQL)</span></span>
<span data-ttu-id="4a87e-103">Determina se una raccolta è vuota.</span><span class="sxs-lookup"><span data-stu-id="4a87e-103">Determines if a collection is empty.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a87e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4a87e-104">Syntax</span></span>  
  
```  
[NOT] EXISTS ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="4a87e-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="4a87e-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="4a87e-106">Qualsiasi espressione valida che restituisce una raccolta.</span><span class="sxs-lookup"><span data-stu-id="4a87e-106">Any valid expression that returns a collection.</span></span>  
  
 <span data-ttu-id="4a87e-107">NOT</span><span class="sxs-lookup"><span data-stu-id="4a87e-107">NOT</span></span>  
 <span data-ttu-id="4a87e-108">Specifica la negazione del risultato di EXISTS.</span><span class="sxs-lookup"><span data-stu-id="4a87e-108">Specifies that the result of EXISTS be negated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a87e-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4a87e-109">Return Value</span></span>  
 `true` <span data-ttu-id="4a87e-110">Se la raccolta non è vuota. in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="4a87e-110">if the collection is not empty; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a87e-111">Note</span><span class="sxs-lookup"><span data-stu-id="4a87e-111">Remarks</span></span>  
 <span data-ttu-id="4a87e-112">EXISTS è uno degli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a87e-112">EXISTS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="4a87e-113">Tutti gli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vengono valutati da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="4a87e-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="4a87e-114">Per informazioni sulla priorità per la [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operatori sui set, vedere [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="4a87e-114">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a87e-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="4a87e-115">Example</span></span>  
 <span data-ttu-id="4a87e-116">Nella query Entity SQL seguente viene usato l'operatore EXISTS per determinare se la raccolta è vuota.</span><span class="sxs-lookup"><span data-stu-id="4a87e-116">The following Entity SQL query uses the EXISTS operator to determine whether the collection is empty.</span></span> <span data-ttu-id="4a87e-117">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="4a87e-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="4a87e-118">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4a87e-118">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="4a87e-119">Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="4a87e-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="4a87e-120">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="4a87e-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EXISTS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#exists)]  
  
## <a name="see-also"></a><span data-ttu-id="4a87e-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a87e-121">See also</span></span>

- [<span data-ttu-id="4a87e-122">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="4a87e-122">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
