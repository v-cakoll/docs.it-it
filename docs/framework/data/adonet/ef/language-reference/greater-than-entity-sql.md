---
title: '&gt; (maggiore di) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 4cea865c-677c-4b06-99a1-010f2ae2394a
ms.openlocfilehash: b9cf4d5445060bbd013ae2d769c407e7f9ee9314
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="gt-greater-than-entity-sql"></a><span data-ttu-id="04524-102">&gt; (maggiore di) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="04524-102">&gt; (Greater Than) (Entity SQL)</span></span>
<span data-ttu-id="04524-103">Consente di confrontare due espressioni per determinare se l'espressione a sinistra ha un valore maggiore di quella a destra.</span><span class="sxs-lookup"><span data-stu-id="04524-103">Compares two expressions to determine whether the left expression has a value greater than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04524-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="04524-104">Syntax</span></span>  
  
```  
expression > expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="04524-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="04524-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="04524-106">Qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="04524-106">Any valid expression.</span></span> <span data-ttu-id="04524-107">Entrambe le espressioni devono contenere tipi di dati convertibili in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="04524-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="04524-108">Tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="04524-108">Result Types</span></span>  
 <span data-ttu-id="04524-109">`true` se l'espressione a sinistra ha un valore maggiore di quella a destra; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="04524-109">`true` if the left expression has a value greater than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04524-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="04524-110">Example</span></span>  
 <span data-ttu-id="04524-111">Nella query Entity SQL seguente viene usato l'operatore di confronto > per confrontare due espressioni e determinare se l'espressione a sinistra ha un valore maggiore di quella a destra.</span><span class="sxs-lookup"><span data-stu-id="04524-111">The following Entity SQL query uses > comparison operator to compare two expressions to determine whether the left expression has a value greater than the right expression.</span></span> <span data-ttu-id="04524-112">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="04524-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="04524-113">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="04524-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="04524-114">Seguire la procedura indicata in [Procedura: eseguire una query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="04524-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="04524-115">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="04524-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#GREATER](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#greater)]  
  
## <a name="see-also"></a><span data-ttu-id="04524-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04524-116">See Also</span></span>  
 [<span data-ttu-id="04524-117">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="04524-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
