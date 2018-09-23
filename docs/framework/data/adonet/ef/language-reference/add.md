---
title: + (Aggiungi)
ms.date: 03/30/2017
ms.assetid: 51769b02-a8f7-4177-9e99-bbd10e77092c
ms.openlocfilehash: a3c41ef8cf393a4d1b1deb362d6a3614558a34ba
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2018
ms.locfileid: "46703791"
---
# <a name="-add"></a><span data-ttu-id="72624-102">+ (addizione)</span><span class="sxs-lookup"><span data-stu-id="72624-102">+ (Add)</span></span>
<span data-ttu-id="72624-103">Esegue l'addizione di due numeri.</span><span class="sxs-lookup"><span data-stu-id="72624-103">Adds two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72624-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="72624-104">Syntax</span></span>  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="72624-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="72624-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="72624-106">Qualsiasi espressione valida con qualsiasi tipo di dati numerici.</span><span class="sxs-lookup"><span data-stu-id="72624-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="72624-107">Tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="72624-107">Result Types</span></span>  
 <span data-ttu-id="72624-108">Tipo di dati ottenuto della promozione implicita del tipo dei due argomenti.</span><span class="sxs-lookup"><span data-stu-id="72624-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="72624-109">Per altre informazioni sulla promozione implicita del tipo, vedere [sistema di tipi](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="72624-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72624-110">Note</span><span class="sxs-lookup"><span data-stu-id="72624-110">Remarks</span></span>  
 <span data-ttu-id="72624-111">Per i tipi EDM.String, l'aggiunta è la concatenazione.</span><span class="sxs-lookup"><span data-stu-id="72624-111">For EDM.String types, addition is concatenation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72624-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="72624-112">Example</span></span>  
 <span data-ttu-id="72624-113">Nella query Entity SQL seguente viene usato l'operatore aritmetico + per sommare due numeri.</span><span class="sxs-lookup"><span data-stu-id="72624-113">The following Entity SQL query uses the + arithmetic operator to add two numbers.</span></span> <span data-ttu-id="72624-114">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="72624-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="72624-115">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="72624-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="72624-116">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="72624-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="72624-117">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="72624-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ADD](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#add)]  
  
## <a name="see-also"></a><span data-ttu-id="72624-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72624-118">See Also</span></span>  
 [<span data-ttu-id="72624-119">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="72624-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="72624-120">Tipi del modello concettuale (CSDL)</span><span class="sxs-lookup"><span data-stu-id="72624-120">Conceptual Model Types (CSDL)</span></span>](https://msdn.microsoft.com/library/987b995f-e429-4569-9559-b4146744def4)
