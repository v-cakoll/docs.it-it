---
title: '! (NOT) (Entity SQL)'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: f3786724280cc077574f37e4d373c85faf5340f3
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="-not-entity-sql"></a><span data-ttu-id="d06a4-103">!</span><span class="sxs-lookup"><span data-stu-id="d06a4-103">!</span></span> <span data-ttu-id="d06a4-104">(NOT) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d06a4-104">(NOT) (Entity SQL)</span></span>
<span data-ttu-id="d06a4-105">Nega un'espressione `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="d06a4-105">Negates a `Boolean` expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d06a4-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d06a4-106">Syntax</span></span>  
  
```  
NOT boolean_expression  
or  
! boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="d06a4-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d06a4-107">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="d06a4-108">Qualsiasi espressione valida che restituisce un valore Boolean.</span><span class="sxs-lookup"><span data-stu-id="d06a4-108">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d06a4-109">Note</span><span class="sxs-lookup"><span data-stu-id="d06a4-109">Remarks</span></span>  
 <span data-ttu-id="d06a4-110">Il punto esclamativo (!) ha la stessa funzionalità dell'operatore NOT.</span><span class="sxs-lookup"><span data-stu-id="d06a4-110">The exclamation point (!) has the same functionality as the NOT operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d06a4-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="d06a4-111">Example</span></span>  
 <span data-ttu-id="d06a4-112">Nella query Entity SQL seguente viene usato l'operatore NOT per negare un'espressione `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="d06a4-112">The following Entity SQL query uses the NOT operator to negates a `Boolean` expression.</span></span> <span data-ttu-id="d06a4-113">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="d06a4-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="d06a4-114">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d06a4-114">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="d06a4-115">Seguire la procedura indicata in [Procedura: eseguire una query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="d06a4-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="d06a4-116">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="d06a4-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NOT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#not)]  
  
## <a name="see-also"></a><span data-ttu-id="d06a4-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d06a4-117">See Also</span></span>  
 [<span data-ttu-id="d06a4-118">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d06a4-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
