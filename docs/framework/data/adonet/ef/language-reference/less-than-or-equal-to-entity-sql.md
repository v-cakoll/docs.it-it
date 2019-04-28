---
title: < = (minore o uguale a) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 7c46da5c-fa09-4d90-adcc-c7e1b769d8e6
ms.openlocfilehash: 7a65984da22d125bdbdd5cfadb5a2051fa3dafdc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61780276"
---
# <a name="-less-than-or-equal-to-entity-sql"></a><span data-ttu-id="ba445-102">\<= (minore o uguale a) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ba445-102">\<= (Less Than or Equal To) (Entity SQL)</span></span>
<span data-ttu-id="ba445-103">Consente di confrontare due espressioni per determinare se l'espressione a sinistra ha un valore minore o uguale a quella a destra.</span><span class="sxs-lookup"><span data-stu-id="ba445-103">Compares two expressions to determine whether the left expression has a value less than or equal to the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba445-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ba445-104">Syntax</span></span>  
  
```  
expression <= expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="ba445-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="ba445-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ba445-106">Qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="ba445-106">Any valid expression.</span></span> <span data-ttu-id="ba445-107">Entrambe le espressioni devono contenere tipi di dati convertibili in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="ba445-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="ba445-108">Tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="ba445-108">Result Types</span></span>  
 <span data-ttu-id="ba445-109">`true` se l'espressione a sinistra ha un valore minore o uguale a quella a destra; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="ba445-109">`true` if the left expression has a value less than or equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba445-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="ba445-110">Example</span></span>  
 <span data-ttu-id="ba445-111">Nella query Entity SQL seguente viene usato l'operatore di confronto <= per confrontare due espressioni e determinare se l'espressione a sinistra ha un valore minore o uguale a quella a destra.</span><span class="sxs-lookup"><span data-stu-id="ba445-111">The following Entity SQL query uses <= comparison operator to compare two expressions to determine whether the left expression has a value less than or equal to the right expression.</span></span> <span data-ttu-id="ba445-112">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="ba445-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ba445-113">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba445-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="ba445-114">Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="ba445-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="ba445-115">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="ba445-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#LESS_OR_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#less_or_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="ba445-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba445-116">See also</span></span>

- [<span data-ttu-id="ba445-117">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="ba445-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
