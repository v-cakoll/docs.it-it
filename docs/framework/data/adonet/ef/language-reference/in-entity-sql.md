---
title: IN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 51662950-ee01-4857-b7b9-311dd8515966
ms.openlocfilehash: e46db63600b6baa03697615a2f5eb9240f55d15e
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833690"
---
# <a name="in-entity-sql"></a><span data-ttu-id="ddb02-102">IN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ddb02-102">IN (Entity SQL)</span></span>
<span data-ttu-id="ddb02-103">Determina se un valore corrisponde a qualsiasi valore in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="ddb02-103">Determines whether a value matches any value in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddb02-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ddb02-104">Syntax</span></span>  
  
```sql  
value [ NOT ] IN expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="ddb02-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="ddb02-105">Arguments</span></span>  
 `value`  
 <span data-ttu-id="ddb02-106">Qualsiasi espressione valida che restituisce il valore di cui trovare la corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="ddb02-106">Any valid expression that returns the value to match.</span></span>  
  
 <span data-ttu-id="ddb02-107">[ NOT ]</span><span class="sxs-lookup"><span data-stu-id="ddb02-107">[ NOT ]</span></span>  
 <span data-ttu-id="ddb02-108">Specifica la negazione del risultato `Boolean` di IN.</span><span class="sxs-lookup"><span data-stu-id="ddb02-108">Specifies that the `Boolean` result of IN be negated.</span></span>  
  
 `expression`  
 <span data-ttu-id="ddb02-109">Qualsiasi espressione valida che restituisce la raccolta da testare per trovare una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="ddb02-109">Any valid expression that returns the collection to test for a match.</span></span> <span data-ttu-id="ddb02-110">Tutte le espressioni devono essere dello stesso tipo o di un tipo di base o derivato comune di `value`.</span><span class="sxs-lookup"><span data-stu-id="ddb02-110">All expressions must be of the same type or of a common base or derived type as `value`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ddb02-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ddb02-111">Return Value</span></span>  
 <span data-ttu-id="ddb02-112">`true` se il valore viene trovato nella raccolta; null se il valore è null o se la raccolta è null; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="ddb02-112">`true` if the value is found in the collection; null if the value is null or the collection is null; otherwise, `false`.</span></span> <span data-ttu-id="ddb02-113">L'utilizzo di NOT IN consente di negare i risultati di IN.</span><span class="sxs-lookup"><span data-stu-id="ddb02-113">Using NOT IN negates the results of IN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ddb02-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="ddb02-114">Example</span></span>  
 <span data-ttu-id="ddb02-115">Nella query Entity SQL seguente viene usato l'operatore IN per determinare se un valore corrisponde a qualsiasi valore in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="ddb02-115">The following Entity SQL query uses the IN operator to determine whether a value matches any value in a collection.</span></span> <span data-ttu-id="ddb02-116">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="ddb02-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ddb02-117">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ddb02-117">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="ddb02-118">Seguire la procedura indicata in [Procedura: eseguire una query che restituisce risultati StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="ddb02-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="ddb02-119">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="ddb02-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#IN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#in)]  
  
## <a name="see-also"></a><span data-ttu-id="ddb02-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ddb02-120">See also</span></span>

- [<span data-ttu-id="ddb02-121">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="ddb02-121">Entity SQL Reference</span></span>](entity-sql-reference.md)
