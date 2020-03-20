---
title: = (uguale a) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 948eb588-7080-4046-bb48-633b007393bf
ms.openlocfilehash: 101dccd40e9197c7cf0795ccb80ded367676842d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150312"
---
# <a name="-equals-entity-sql"></a><span data-ttu-id="e103e-102">= (uguale a) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e103e-102">= (Equals) (Entity SQL)</span></span>
<span data-ttu-id="e103e-103">Consente di confrontare due espressioni per verificare se sono uguali.</span><span class="sxs-lookup"><span data-stu-id="e103e-103">Compares the equality of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e103e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e103e-104">Syntax</span></span>  
  
```sql  
expression = expression  
-- or
expression == expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="e103e-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="e103e-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="e103e-106">Qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="e103e-106">Any valid expression.</span></span> <span data-ttu-id="e103e-107">È necessario che il tipo di dati di entrambe le espressioni possa essere convertito in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="e103e-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="e103e-108">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="e103e-108">Result Types</span></span>  
 <span data-ttu-id="e103e-109">`true` se l'espressione a sinistra è uguale a quella a destra; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="e103e-109">`true` if the left expression is equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e103e-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e103e-110">Remarks</span></span>  
 <span data-ttu-id="e103e-111">L'operatore == è equivalente a =.</span><span class="sxs-lookup"><span data-stu-id="e103e-111">The == operator is equivalent to =.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e103e-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="e103e-112">Example</span></span>  
 <span data-ttu-id="e103e-113">Nella query Entity SQL seguente viene usato l'operatore di confronto = per confrontare due espressioni e verificare se sono uguali.</span><span class="sxs-lookup"><span data-stu-id="e103e-113">The following Entity SQL query uses = comparison operator to compare the equality of two expressions.</span></span> <span data-ttu-id="e103e-114">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="e103e-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="e103e-115">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e103e-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="e103e-116">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="e103e-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="e103e-117">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="e103e-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#equals)]  
  
## <a name="see-also"></a><span data-ttu-id="e103e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e103e-118">See also</span></span>

- [<span data-ttu-id="e103e-119">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e103e-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
