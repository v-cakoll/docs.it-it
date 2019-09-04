---
title: '> (Maggiore di) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 4cea865c-677c-4b06-99a1-010f2ae2394a
ms.openlocfilehash: 0b57f36681575ccbe3239220e89804c804f13f39
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250890"
---
# <a name="-greater-than-entity-sql"></a><span data-ttu-id="1e6df-102">> (Maggiore di) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="1e6df-102">> (Greater Than) (Entity SQL)</span></span>
<span data-ttu-id="1e6df-103">Consente di confrontare due espressioni per determinare se l'espressione a sinistra ha un valore maggiore di quella a destra.</span><span class="sxs-lookup"><span data-stu-id="1e6df-103">Compares two expressions to determine whether the left expression has a value greater than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e6df-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1e6df-104">Syntax</span></span>  
  
```  
expression > expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="1e6df-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="1e6df-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="1e6df-106">Qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="1e6df-106">Any valid expression.</span></span> <span data-ttu-id="1e6df-107">Entrambe le espressioni devono contenere tipi di dati convertibili in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="1e6df-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="1e6df-108">Tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="1e6df-108">Result Types</span></span>  
 <span data-ttu-id="1e6df-109">`true` se l'espressione a sinistra ha un valore maggiore di quella a destra; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="1e6df-109">`true` if the left expression has a value greater than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e6df-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="1e6df-110">Example</span></span>  
 <span data-ttu-id="1e6df-111">Nella query Entity SQL seguente viene usato l'operatore di confronto > per confrontare due espressioni e determinare se l'espressione a sinistra ha un valore maggiore di quella a destra.</span><span class="sxs-lookup"><span data-stu-id="1e6df-111">The following Entity SQL query uses > comparison operator to compare two expressions to determine whether the left expression has a value greater than the right expression.</span></span> <span data-ttu-id="1e6df-112">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="1e6df-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="1e6df-113">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1e6df-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="1e6df-114">Attenersi alla procedura descritta [in procedura: Eseguire una query che restituisce i risultati](../how-to-execute-a-query-that-returns-structuraltype-results.md)di StructuralType.</span><span class="sxs-lookup"><span data-stu-id="1e6df-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="1e6df-115">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="1e6df-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#GREATER](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#greater)]  
  
## <a name="see-also"></a><span data-ttu-id="1e6df-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e6df-116">See also</span></span>

- [<span data-ttu-id="1e6df-117">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="1e6df-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
