---
title: EXISTS (Entity SQL)
ms.date: 03/30/2017
ms.assetid: d28ead43-4afb-4bdc-af64-efd2e05005d7
ms.openlocfilehash: 44f128a292b013fd3a3a80efdd2d10a63e3cfb07
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833830"
---
# <a name="exists-entity-sql"></a><span data-ttu-id="a3206-102">EXISTS (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a3206-102">EXISTS (Entity SQL)</span></span>
<span data-ttu-id="a3206-103">Determina se una raccolta è vuota.</span><span class="sxs-lookup"><span data-stu-id="a3206-103">Determines if a collection is empty.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3206-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a3206-104">Syntax</span></span>  
  
```sql  
[NOT] EXISTS ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="a3206-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a3206-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="a3206-106">Qualsiasi espressione valida che restituisce una raccolta.</span><span class="sxs-lookup"><span data-stu-id="a3206-106">Any valid expression that returns a collection.</span></span>  
  
 <span data-ttu-id="a3206-107">NOT</span><span class="sxs-lookup"><span data-stu-id="a3206-107">NOT</span></span>  
 <span data-ttu-id="a3206-108">Specifica la negazione del risultato di EXISTS.</span><span class="sxs-lookup"><span data-stu-id="a3206-108">Specifies that the result of EXISTS be negated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3206-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a3206-109">Return Value</span></span>  
 <span data-ttu-id="a3206-110">`true` se la raccolta non è vuota; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="a3206-110">`true` if the collection is not empty; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3206-111">Note</span><span class="sxs-lookup"><span data-stu-id="a3206-111">Remarks</span></span>  
 <span data-ttu-id="a3206-112">EXISTS è uno degli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3206-112">EXISTS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="a3206-113">Tutti gli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vengono valutati da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="a3206-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="a3206-114">Per informazioni sulla precedenza per gli operatori di set [!INCLUDE[esql](../../../../../../includes/esql-md.md)], vedere [except](except-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="a3206-114">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3206-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="a3206-115">Example</span></span>  
 <span data-ttu-id="a3206-116">Nella query Entity SQL seguente viene usato l'operatore EXISTS per determinare se la raccolta è vuota.</span><span class="sxs-lookup"><span data-stu-id="a3206-116">The following Entity SQL query uses the EXISTS operator to determine whether the collection is empty.</span></span> <span data-ttu-id="a3206-117">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="a3206-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="a3206-118">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a3206-118">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="a3206-119">Seguire la procedura descritta in [How per: Eseguire una query che restituisce i risultati di StructuralType @ no__t-0.</span><span class="sxs-lookup"><span data-stu-id="a3206-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="a3206-120">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="a3206-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#EXISTS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#exists)]  
  
## <a name="see-also"></a><span data-ttu-id="a3206-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3206-121">See also</span></span>

- [<span data-ttu-id="a3206-122">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a3206-122">Entity SQL Reference</span></span>](entity-sql-reference.md)
