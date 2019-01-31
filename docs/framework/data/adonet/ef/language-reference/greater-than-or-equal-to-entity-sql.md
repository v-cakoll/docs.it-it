---
title: '>= (Maggiore o uguale a) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 70780ac4-0123-4da8-b731-8af856daffe3
ms.openlocfilehash: 4b7b2aa7be0b978fb6b1317393fb3c6e9a87c621
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55289013"
---
# <a name="-greater-than-or-equal-to-entity-sql"></a><span data-ttu-id="ce5e2-102">>= (maggiore di o uguale a) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ce5e2-102">>= (Greater Than or Equal To) (Entity SQL)</span></span>
<span data-ttu-id="ce5e2-103">Consente di confrontare due espressioni per determinare se l'espressione a sinistra ha un valore maggiore o uguale a quella a destra.</span><span class="sxs-lookup"><span data-stu-id="ce5e2-103">Compares two expressions to determine whether the left expression has a value greater than or equal to the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce5e2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce5e2-104">Syntax</span></span>  
  
```  
expression >= expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="ce5e2-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="ce5e2-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ce5e2-106">Qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="ce5e2-106">Any valid expression.</span></span> <span data-ttu-id="ce5e2-107">Entrambe le espressioni devono contenere tipi di dati convertibili in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="ce5e2-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="ce5e2-108">Tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="ce5e2-108">Result Types</span></span>  
 <span data-ttu-id="ce5e2-109">`true` se l'espressione a sinistra ha un valore maggiore o uguale a quella a destra; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="ce5e2-109">`true` if the left expression has a value greater than or equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce5e2-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="ce5e2-110">Example</span></span>  
 <span data-ttu-id="ce5e2-111">Nella query Entity SQL seguente viene usato l'operatore di confronto >= per confrontare due espressioni e determinare se l'espressione a sinistra ha un valore maggiore o uguale a quella a destra.</span><span class="sxs-lookup"><span data-stu-id="ce5e2-111">The following Entity SQL query uses >= comparison operator to compare two expressions to determine whether the left expression has a value greater than or equal to the right expression.</span></span> <span data-ttu-id="ce5e2-112">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="ce5e2-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ce5e2-113">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ce5e2-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="ce5e2-114">Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="ce5e2-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="ce5e2-115">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="ce5e2-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#GREATER_OR_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#greater_or_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="ce5e2-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce5e2-116">See also</span></span>
- [<span data-ttu-id="ce5e2-117">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="ce5e2-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
