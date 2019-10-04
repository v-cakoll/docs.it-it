---
title: = (uguale a) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 948eb588-7080-4046-bb48-633b007393bf
ms.openlocfilehash: 5cdfd35450514a9699a39cf78f64c0fa6b7d5f39
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833843"
---
# <a name="-equals-entity-sql"></a><span data-ttu-id="a114c-102">= (uguale a) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a114c-102">= (Equals) (Entity SQL)</span></span>
<span data-ttu-id="a114c-103">Consente di confrontare due espressioni per verificare se sono uguali.</span><span class="sxs-lookup"><span data-stu-id="a114c-103">Compares the equality of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a114c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a114c-104">Syntax</span></span>  
  
```sql  
expression = expression  
-- or   
expression == expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="a114c-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a114c-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="a114c-106">Qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="a114c-106">Any valid expression.</span></span> <span data-ttu-id="a114c-107">Entrambe le espressioni devono contenere tipi di dati convertibili in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="a114c-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="a114c-108">Tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="a114c-108">Result Types</span></span>  
 <span data-ttu-id="a114c-109">`true` se l'espressione a sinistra è uguale a quella a destra; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="a114c-109">`true` if the left expression is equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a114c-110">Note</span><span class="sxs-lookup"><span data-stu-id="a114c-110">Remarks</span></span>  
 <span data-ttu-id="a114c-111">L'operatore == è equivalente a =.</span><span class="sxs-lookup"><span data-stu-id="a114c-111">The == operator is equivalent to =.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a114c-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="a114c-112">Example</span></span>  
 <span data-ttu-id="a114c-113">Nella query Entity SQL seguente viene usato l'operatore di confronto = per confrontare due espressioni e verificare se sono uguali.</span><span class="sxs-lookup"><span data-stu-id="a114c-113">The following Entity SQL query uses = comparison operator to compare the equality of two expressions.</span></span> <span data-ttu-id="a114c-114">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="a114c-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="a114c-115">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a114c-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="a114c-116">Seguire la procedura descritta in [How per: Eseguire una query che restituisce i risultati di StructuralType @ no__t-0.</span><span class="sxs-lookup"><span data-stu-id="a114c-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="a114c-117">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="a114c-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#equals)]  
  
## <a name="see-also"></a><span data-ttu-id="a114c-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a114c-118">See also</span></span>

- [<span data-ttu-id="a114c-119">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a114c-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
