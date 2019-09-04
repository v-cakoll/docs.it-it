---
title: '- Sottrarre (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: bc4327f9-09c0-438f-a008-927c5c478040
ms.openlocfilehash: 8b5cfee4c82757e55babdf1ad14f6cf3c743a5a2
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249009"
---
# <a name="--subtract-entity-sql"></a><span data-ttu-id="9507b-102">- (sottrazione) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="9507b-102">- (Subtract) (Entity SQL)</span></span>
<span data-ttu-id="9507b-103">Esegue la sottrazione di due numeri.</span><span class="sxs-lookup"><span data-stu-id="9507b-103">Subtracts two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9507b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9507b-104">Syntax</span></span>  
  
```  
expression - expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="9507b-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="9507b-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="9507b-106">Qualsiasi espressione valida con qualsiasi tipo di dati numerici.</span><span class="sxs-lookup"><span data-stu-id="9507b-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="9507b-107">Tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="9507b-107">Result Types</span></span>  
 <span data-ttu-id="9507b-108">Tipo di dati ottenuto della promozione implicita del tipo dei due argomenti.</span><span class="sxs-lookup"><span data-stu-id="9507b-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="9507b-109">Per ulteriori informazioni sull'innalzamento di tipo implicito, vedere [System Type](type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="9507b-109">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9507b-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="9507b-110">Example</span></span>  
 <span data-ttu-id="9507b-111">Nella query Entity SQL seguente viene usato l'operatore aritmetico - per sottrarre due numeri.</span><span class="sxs-lookup"><span data-stu-id="9507b-111">The following Entity SQL query uses the - arithmetic operator to subtract two numbers.</span></span> <span data-ttu-id="9507b-112">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="9507b-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="9507b-113">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9507b-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="9507b-114">Attenersi alla procedura descritta [in procedura: Eseguire una query che restituisce i risultati](../how-to-execute-a-query-that-returns-structuraltype-results.md)di StructuralType.</span><span class="sxs-lookup"><span data-stu-id="9507b-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="9507b-115">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="9507b-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#SUBTRACT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#subtract)]  
  
## <a name="see-also"></a><span data-ttu-id="9507b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9507b-116">See also</span></span>

- [<span data-ttu-id="9507b-117">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="9507b-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
