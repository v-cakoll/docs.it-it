---
title: '> (Maggiore di) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 4cea865c-677c-4b06-99a1-010f2ae2394a
ms.openlocfilehash: 992e1b7cf4733266f606f8357c71d72722b04896
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127127"
---
# <a name="-greater-than-entity-sql"></a><span data-ttu-id="859a4-102">> (Maggiore di) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="859a4-102">> (Greater Than) (Entity SQL)</span></span>
<span data-ttu-id="859a4-103">Consente di confrontare due espressioni per determinare se l'espressione a sinistra ha un valore maggiore di quella a destra.</span><span class="sxs-lookup"><span data-stu-id="859a4-103">Compares two expressions to determine whether the left expression has a value greater than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="859a4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="859a4-104">Syntax</span></span>  
  
```  
expression > expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="859a4-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="859a4-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="859a4-106">Qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="859a4-106">Any valid expression.</span></span> <span data-ttu-id="859a4-107">Entrambe le espressioni devono contenere tipi di dati convertibili in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="859a4-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="859a4-108">Tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="859a4-108">Result Types</span></span>  
 `true` <span data-ttu-id="859a4-109">Se l'espressione a sinistra ha un valore maggiore rispetto all'espressione a destra; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="859a4-109">if the left expression has a value greater than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="859a4-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="859a4-110">Example</span></span>  
 <span data-ttu-id="859a4-111">Nella query Entity SQL seguente viene usato l'operatore di confronto > per confrontare due espressioni e determinare se l'espressione a sinistra ha un valore maggiore di quella a destra.</span><span class="sxs-lookup"><span data-stu-id="859a4-111">The following Entity SQL query uses > comparison operator to compare two expressions to determine whether the left expression has a value greater than the right expression.</span></span> <span data-ttu-id="859a4-112">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="859a4-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="859a4-113">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="859a4-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="859a4-114">Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="859a4-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="859a4-115">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="859a4-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#GREATER](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#greater)]  
  
## <a name="see-also"></a><span data-ttu-id="859a4-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="859a4-116">See also</span></span>

- [<span data-ttu-id="859a4-117">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="859a4-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
