---
title: EXCEPT (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 69cc23e5-3f8f-4b49-b20e-2f84ff11c80d
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 546503d3fc51c863779c26f363721bf81be054b9
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="except-entity-sql"></a><span data-ttu-id="8120e-102">EXCEPT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="8120e-102">EXCEPT (Entity SQL)</span></span>
<span data-ttu-id="8120e-103">Restituisce una raccolta di tutti i valori distinti dell'espressione di query a sinistra dell'operando EXCEPT che non vengono restituiti anche dall'espressione di query a destra dell'operando EXCEPT.</span><span class="sxs-lookup"><span data-stu-id="8120e-103">Returns a collection of any distinct values from the query expression to the left of the EXCEPT operand that are not also returned from the query expression to the right of the EXCEPT operand.</span></span> <span data-ttu-id="8120e-104">Tutte le espressioni devono essere dello stesso tipo o di un tipo di base o derivato comune di `expression`.</span><span class="sxs-lookup"><span data-stu-id="8120e-104">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8120e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8120e-105">Syntax</span></span>  
  
```  
expression EXCEPT expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="8120e-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="8120e-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="8120e-107">Qualsiasi espressione di query valida che restituisce una raccolta da confrontare con la raccolta restituita da un'altra espressione di query.</span><span class="sxs-lookup"><span data-stu-id="8120e-107">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8120e-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8120e-108">Return Value</span></span>  
 <span data-ttu-id="8120e-109">Raccolta dello stesso tipo o di un tipo di base o derivato comune di `expression`.</span><span class="sxs-lookup"><span data-stu-id="8120e-109">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8120e-110">Note</span><span class="sxs-lookup"><span data-stu-id="8120e-110">Remarks</span></span>  
 <span data-ttu-id="8120e-111">EXCEPT è uno degli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8120e-111">EXCEPT is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="8120e-112">Tutti gli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vengono valutati da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="8120e-112">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="8120e-113">Nella tabella seguente viene indicata la precedenza tra gli operatori dei set [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8120e-113">The following table shows the precedence of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
|<span data-ttu-id="8120e-114">Precedenza</span><span class="sxs-lookup"><span data-stu-id="8120e-114">Precedence</span></span>|<span data-ttu-id="8120e-115">Operatori</span><span class="sxs-lookup"><span data-stu-id="8120e-115">Operators</span></span>|  
|----------------|---------------|  
|<span data-ttu-id="8120e-116">Più alta</span><span class="sxs-lookup"><span data-stu-id="8120e-116">Highest</span></span>|<span data-ttu-id="8120e-117">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="8120e-117">INTERSECT</span></span>|  
||<span data-ttu-id="8120e-118">UNION</span><span class="sxs-lookup"><span data-stu-id="8120e-118">UNION</span></span><br /><br /> <span data-ttu-id="8120e-119">UNION ALL</span><span class="sxs-lookup"><span data-stu-id="8120e-119">UNION ALL</span></span>|  
||<span data-ttu-id="8120e-120">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="8120e-120">EXCEPT</span></span>|  
|<span data-ttu-id="8120e-121">Più bassa</span><span class="sxs-lookup"><span data-stu-id="8120e-121">Lowest</span></span>|<span data-ttu-id="8120e-122">EXISTS</span><span class="sxs-lookup"><span data-stu-id="8120e-122">EXISTS</span></span><br /><br /> <span data-ttu-id="8120e-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="8120e-123">OVERLAPS</span></span><br /><br /> <span data-ttu-id="8120e-124">FLATTEN</span><span class="sxs-lookup"><span data-stu-id="8120e-124">FLATTEN</span></span><br /><br /> <span data-ttu-id="8120e-125">SET</span><span class="sxs-lookup"><span data-stu-id="8120e-125">SET</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8120e-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="8120e-126">Example</span></span>  
 <span data-ttu-id="8120e-127">Nella query Entity SQL seguente viene usato l'operatore EXCEPT per restituire una raccolta di tutti i valori distinti da due espressioni di query.</span><span class="sxs-lookup"><span data-stu-id="8120e-127">The following Entity SQL query uses the EXCEPT operator to return a collection of any distinct values from two query expressions.</span></span> <span data-ttu-id="8120e-128">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="8120e-128">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="8120e-129">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8120e-129">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="8120e-130">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="8120e-130">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="8120e-131">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="8120e-131">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EXCEPT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#except)]  
  
## <a name="see-also"></a><span data-ttu-id="8120e-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8120e-132">See Also</span></span>  
 [<span data-ttu-id="8120e-133">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="8120e-133">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
