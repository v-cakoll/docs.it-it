---
title: '- (Sottrazione) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: bc4327f9-09c0-438f-a008-927c5c478040
ms.openlocfilehash: 2e4c08788ea57000e189c8371f0494641931184b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59316687"
---
# <a name="--subtract-entity-sql"></a><span data-ttu-id="ad263-102">- (sottrazione) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ad263-102">- (Subtract) (Entity SQL)</span></span>
<span data-ttu-id="ad263-103">Esegue la sottrazione di due numeri.</span><span class="sxs-lookup"><span data-stu-id="ad263-103">Subtracts two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad263-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ad263-104">Syntax</span></span>  
  
```  
expression - expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="ad263-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="ad263-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ad263-106">Qualsiasi espressione valida con qualsiasi tipo di dati numerici.</span><span class="sxs-lookup"><span data-stu-id="ad263-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="ad263-107">Tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="ad263-107">Result Types</span></span>  
 <span data-ttu-id="ad263-108">Tipo di dati ottenuto della promozione implicita del tipo dei due argomenti.</span><span class="sxs-lookup"><span data-stu-id="ad263-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="ad263-109">Per altre informazioni sulla promozione implicita del tipo, vedere [sistema di tipi](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="ad263-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad263-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="ad263-110">Example</span></span>  
 <span data-ttu-id="ad263-111">Nella query Entity SQL seguente viene usato l'operatore aritmetico - per sottrarre due numeri.</span><span class="sxs-lookup"><span data-stu-id="ad263-111">The following Entity SQL query uses the - arithmetic operator to subtract two numbers.</span></span> <span data-ttu-id="ad263-112">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="ad263-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ad263-113">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ad263-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="ad263-114">Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="ad263-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="ad263-115">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="ad263-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#SUBTRACT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#subtract)]  
  
## <a name="see-also"></a><span data-ttu-id="ad263-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad263-116">See also</span></span>

- [<span data-ttu-id="ad263-117">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="ad263-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
