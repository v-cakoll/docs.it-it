---
title: '&lt;= (minore o uguale a) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 7c46da5c-fa09-4d90-adcc-c7e1b769d8e6
ms.openlocfilehash: dd861bf3490794a7a54a09719ae4ae377d0e2861
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="lt-less-than-or-equal-to-entity-sql"></a><span data-ttu-id="e9460-102">&lt;= (minore o uguale a) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e9460-102">&lt;= (Less Than or Equal To) (Entity SQL)</span></span>
<span data-ttu-id="e9460-103">Consente di confrontare due espressioni per determinare se l'espressione a sinistra ha un valore minore o uguale a quella a destra.</span><span class="sxs-lookup"><span data-stu-id="e9460-103">Compares two expressions to determine whether the left expression has a value less than or equal to the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9460-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e9460-104">Syntax</span></span>  
  
```  
expression <= expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="e9460-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="e9460-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="e9460-106">Qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="e9460-106">Any valid expression.</span></span> <span data-ttu-id="e9460-107">Entrambe le espressioni devono contenere tipi di dati convertibili in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="e9460-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="e9460-108">Tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="e9460-108">Result Types</span></span>  
 <span data-ttu-id="e9460-109">`true` se l'espressione a sinistra ha un valore minore o uguale a quella a destra; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="e9460-109">`true` if the left expression has a value less than or equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9460-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="e9460-110">Example</span></span>  
 <span data-ttu-id="e9460-111">Nella query Entity SQL seguente viene usato l'operatore di confronto <= per confrontare due espressioni e determinare se l'espressione a sinistra ha un valore minore o uguale a quella a destra.</span><span class="sxs-lookup"><span data-stu-id="e9460-111">The following Entity SQL query uses <= comparison operator to compare two expressions to determine whether the left expression has a value less than or equal to the right expression.</span></span> <span data-ttu-id="e9460-112">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="e9460-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="e9460-113">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e9460-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="e9460-114">Seguire la procedura indicata in [Procedura: eseguire una query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="e9460-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="e9460-115">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="e9460-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#LESS_OR_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#less_or_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="e9460-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9460-116">See Also</span></span>  
 [<span data-ttu-id="e9460-117">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e9460-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
