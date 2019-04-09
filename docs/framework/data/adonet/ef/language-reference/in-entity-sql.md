---
title: IN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 51662950-ee01-4857-b7b9-311dd8515966
ms.openlocfilehash: f4fa8cbc07513321e59b93503b59af172c0a6f05
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211322"
---
# <a name="in-entity-sql"></a><span data-ttu-id="98223-102">IN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="98223-102">IN (Entity SQL)</span></span>
<span data-ttu-id="98223-103">Determina se un valore corrisponde a qualsiasi valore in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="98223-103">Determines whether a value matches any value in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98223-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="98223-104">Syntax</span></span>  
  
```  
value [ NOT ] IN expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="98223-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="98223-105">Arguments</span></span>  
 `value`  
 <span data-ttu-id="98223-106">Qualsiasi espressione valida che restituisce il valore di cui trovare la corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="98223-106">Any valid expression that returns the value to match.</span></span>  
  
 <span data-ttu-id="98223-107">[ NOT ]</span><span class="sxs-lookup"><span data-stu-id="98223-107">[ NOT ]</span></span>  
 <span data-ttu-id="98223-108">Specifica la negazione del risultato `Boolean` di IN.</span><span class="sxs-lookup"><span data-stu-id="98223-108">Specifies that the `Boolean` result of IN be negated.</span></span>  
  
 `expression`  
 <span data-ttu-id="98223-109">Qualsiasi espressione valida che restituisce la raccolta da testare per trovare una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="98223-109">Any valid expression that returns the collection to test for a match.</span></span> <span data-ttu-id="98223-110">Tutte le espressioni devono essere dello stesso tipo o di un tipo di base o derivato comune di `value`.</span><span class="sxs-lookup"><span data-stu-id="98223-110">All expressions must be of the same type or of a common base or derived type as `value`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="98223-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="98223-111">Return Value</span></span>  
 `true` <span data-ttu-id="98223-112">Se il valore viene trovato nella raccolta. null se il valore è null o la raccolta è null. in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="98223-112">if the value is found in the collection; null if the value is null or the collection is null; otherwise, `false`.</span></span> <span data-ttu-id="98223-113">L'utilizzo di NOT IN consente di negare i risultati di IN.</span><span class="sxs-lookup"><span data-stu-id="98223-113">Using NOT IN negates the results of IN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98223-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="98223-114">Example</span></span>  
 <span data-ttu-id="98223-115">Nella query Entity SQL seguente viene usato l'operatore IN per determinare se un valore corrisponde a qualsiasi valore in una raccolta.</span><span class="sxs-lookup"><span data-stu-id="98223-115">The following Entity SQL query uses the IN operator to determine whether a value matches any value in a collection.</span></span> <span data-ttu-id="98223-116">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="98223-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="98223-117">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="98223-117">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="98223-118">Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="98223-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="98223-119">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="98223-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#IN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#in)]  
  
## <a name="see-also"></a><span data-ttu-id="98223-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98223-120">See also</span></span>

- [<span data-ttu-id="98223-121">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="98223-121">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
