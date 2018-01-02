---
title: IN (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51662950-ee01-4857-b7b9-311dd8515966
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 00d5a309a68ad7c1c5f363d6df3cca7a0e90ce81
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="in-entity-sql"></a><span data-ttu-id="5f892-102">IN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5f892-102">IN (Entity SQL)</span></span>
<span data-ttu-id="5f892-103">Determina se un valore corrisponde a qualsiasi valore in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="5f892-103">Determines whether a value matches any value in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f892-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5f892-104">Syntax</span></span>  
  
```  
value [ NOT ] IN expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="5f892-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="5f892-105">Arguments</span></span>  
 `value`  
 <span data-ttu-id="5f892-106">Qualsiasi espressione valida che restituisce il valore di cui trovare la corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="5f892-106">Any valid expression that returns the value to match.</span></span>  
  
 <span data-ttu-id="5f892-107">[ NOT ]</span><span class="sxs-lookup"><span data-stu-id="5f892-107">[ NOT ]</span></span>  
 <span data-ttu-id="5f892-108">Specifica la negazione del risultato `Boolean` di IN.</span><span class="sxs-lookup"><span data-stu-id="5f892-108">Specifies that the `Boolean` result of IN be negated.</span></span>  
  
 `expression`  
 <span data-ttu-id="5f892-109">Qualsiasi espressione valida che restituisce la raccolta da testare per trovare una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="5f892-109">Any valid expression that returns the collection to test for a match.</span></span> <span data-ttu-id="5f892-110">Tutte le espressioni devono essere dello stesso tipo o di un tipo di base o derivato comune di `value`.</span><span class="sxs-lookup"><span data-stu-id="5f892-110">All expressions must be of the same type or of a common base or derived type as `value`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f892-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5f892-111">Return Value</span></span>  
 <span data-ttu-id="5f892-112">`true` se il valore viene trovato nella raccolta; null se il valore è null o se la raccolta è null; in caso contrario `false`.</span><span class="sxs-lookup"><span data-stu-id="5f892-112">`true` if the value is found in the collection; null if the value is null or the collection is null; otherwise, `false`.</span></span> <span data-ttu-id="5f892-113">L'utilizzo di NOT IN consente di negare i risultati di IN.</span><span class="sxs-lookup"><span data-stu-id="5f892-113">Using NOT IN negates the results of IN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f892-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="5f892-114">Example</span></span>  
 <span data-ttu-id="5f892-115">Nella query Entity SQL seguente viene usato l'operatore IN per determinare se un valore corrisponde a qualsiasi valore in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="5f892-115">The following Entity SQL query uses the IN operator to determine whether a value matches any value in a collection.</span></span> <span data-ttu-id="5f892-116">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="5f892-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="5f892-117">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5f892-117">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="5f892-118">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="5f892-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="5f892-119">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="5f892-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#IN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#in)]  
  
## <a name="see-also"></a><span data-ttu-id="5f892-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f892-120">See Also</span></span>  
 [<span data-ttu-id="5f892-121">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5f892-121">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
