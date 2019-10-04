---
title: EXCEPT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 69cc23e5-3f8f-4b49-b20e-2f84ff11c80d
ms.openlocfilehash: c4df8c2b72ee60a425c98c64a13a1e2d43d4506e
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833867"
---
# <a name="except-entity-sql"></a><span data-ttu-id="99afa-102">EXCEPT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="99afa-102">EXCEPT (Entity SQL)</span></span>
<span data-ttu-id="99afa-103">Restituisce una raccolta di tutti i valori distinti dell'espressione di query a sinistra dell'operando EXCEPT che non vengono restituiti anche dall'espressione di query a destra dell'operando EXCEPT.</span><span class="sxs-lookup"><span data-stu-id="99afa-103">Returns a collection of any distinct values from the query expression to the left of the EXCEPT operand that are not also returned from the query expression to the right of the EXCEPT operand.</span></span> <span data-ttu-id="99afa-104">Tutte le espressioni devono essere dello stesso tipo o di un tipo di base o derivato comune di `expression`.</span><span class="sxs-lookup"><span data-stu-id="99afa-104">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99afa-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="99afa-105">Syntax</span></span>  
  
```sql  
expression EXCEPT expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="99afa-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="99afa-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="99afa-107">Qualsiasi espressione di query valida che restituisce una raccolta da confrontare con la raccolta restituita da un'altra espressione di query.</span><span class="sxs-lookup"><span data-stu-id="99afa-107">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99afa-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="99afa-108">Return Value</span></span>  
 <span data-ttu-id="99afa-109">Raccolta dello stesso tipo o di un tipo di base o derivato comune di `expression`.</span><span class="sxs-lookup"><span data-stu-id="99afa-109">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99afa-110">Note</span><span class="sxs-lookup"><span data-stu-id="99afa-110">Remarks</span></span>  
 <span data-ttu-id="99afa-111">EXCEPT è uno degli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="99afa-111">EXCEPT is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="99afa-112">Tutti gli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vengono valutati da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="99afa-112">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="99afa-113">Nella tabella seguente viene indicata la precedenza tra gli operatori dei set [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="99afa-113">The following table shows the precedence of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
|<span data-ttu-id="99afa-114">Precedenza</span><span class="sxs-lookup"><span data-stu-id="99afa-114">Precedence</span></span>|<span data-ttu-id="99afa-115">Operatori</span><span class="sxs-lookup"><span data-stu-id="99afa-115">Operators</span></span>|  
|----------------|---------------|  
|<span data-ttu-id="99afa-116">Più alta</span><span class="sxs-lookup"><span data-stu-id="99afa-116">Highest</span></span>|<span data-ttu-id="99afa-117">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="99afa-117">INTERSECT</span></span>|  
||<span data-ttu-id="99afa-118">UNION</span><span class="sxs-lookup"><span data-stu-id="99afa-118">UNION</span></span><br /><br /> <span data-ttu-id="99afa-119">UNION ALL</span><span class="sxs-lookup"><span data-stu-id="99afa-119">UNION ALL</span></span>|  
||<span data-ttu-id="99afa-120">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="99afa-120">EXCEPT</span></span>|  
|<span data-ttu-id="99afa-121">Più bassa</span><span class="sxs-lookup"><span data-stu-id="99afa-121">Lowest</span></span>|<span data-ttu-id="99afa-122">EXISTS</span><span class="sxs-lookup"><span data-stu-id="99afa-122">EXISTS</span></span><br /><br /> <span data-ttu-id="99afa-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="99afa-123">OVERLAPS</span></span><br /><br /> <span data-ttu-id="99afa-124">FLATTEN</span><span class="sxs-lookup"><span data-stu-id="99afa-124">FLATTEN</span></span><br /><br /> <span data-ttu-id="99afa-125">SET</span><span class="sxs-lookup"><span data-stu-id="99afa-125">SET</span></span>|  
  
## <a name="example"></a><span data-ttu-id="99afa-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="99afa-126">Example</span></span>  
 <span data-ttu-id="99afa-127">Nella query Entity SQL seguente viene usato l'operatore EXCEPT per restituire una raccolta di tutti i valori distinti da due espressioni di query.</span><span class="sxs-lookup"><span data-stu-id="99afa-127">The following Entity SQL query uses the EXCEPT operator to return a collection of any distinct values from two query expressions.</span></span> <span data-ttu-id="99afa-128">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="99afa-128">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="99afa-129">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="99afa-129">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="99afa-130">Seguire la procedura descritta in [How per: Eseguire una query che restituisce i risultati di StructuralType @ no__t-0.</span><span class="sxs-lookup"><span data-stu-id="99afa-130">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="99afa-131">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="99afa-131">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#EXCEPT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#except)]  
  
## <a name="see-also"></a><span data-ttu-id="99afa-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99afa-132">See also</span></span>

- [<span data-ttu-id="99afa-133">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="99afa-133">Entity SQL Reference</span></span>](entity-sql-reference.md)
