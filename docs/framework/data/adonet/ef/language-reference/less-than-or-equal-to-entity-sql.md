---
title: < = (minore o uguale a) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 7c46da5c-fa09-4d90-adcc-c7e1b769d8e6
ms.openlocfilehash: b3c8fef47b06b9fdd0a1619a9e56d3d916d9dd2d
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319641"
---
# <a name="-less-than-or-equal-to-entity-sql"></a><span data-ttu-id="9fc26-102">\<= (minore o uguale a) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="9fc26-102">\<= (Less Than or Equal To) (Entity SQL)</span></span>
<span data-ttu-id="9fc26-103">Consente di confrontare due espressioni per determinare se l'espressione a sinistra ha un valore minore o uguale a quella a destra.</span><span class="sxs-lookup"><span data-stu-id="9fc26-103">Compares two expressions to determine whether the left expression has a value less than or equal to the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fc26-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9fc26-104">Syntax</span></span>  
  
```sql  
expression <= expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="9fc26-105">argomenti</span><span class="sxs-lookup"><span data-stu-id="9fc26-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="9fc26-106">Qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="9fc26-106">Any valid expression.</span></span> <span data-ttu-id="9fc26-107">Entrambe le espressioni devono contenere tipi di dati convertibili in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="9fc26-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="9fc26-108">Tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="9fc26-108">Result Types</span></span>  
 <span data-ttu-id="9fc26-109">`true` se l'espressione a sinistra ha un valore minore o uguale a quella a destra; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="9fc26-109">`true` if the left expression has a value less than or equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fc26-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="9fc26-110">Example</span></span>  
 <span data-ttu-id="9fc26-111">Nella query Entity SQL seguente viene usato l'operatore di confronto <= per confrontare due espressioni e determinare se l'espressione a sinistra ha un valore minore o uguale a quella a destra.</span><span class="sxs-lookup"><span data-stu-id="9fc26-111">The following Entity SQL query uses <= comparison operator to compare two expressions to determine whether the left expression has a value less than or equal to the right expression.</span></span> <span data-ttu-id="9fc26-112">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="9fc26-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="9fc26-113">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9fc26-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="9fc26-114">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="9fc26-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="9fc26-115">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="9fc26-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#LESS_OR_EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#less_or_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="9fc26-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9fc26-116">See also</span></span>

- [<span data-ttu-id="9fc26-117">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="9fc26-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
