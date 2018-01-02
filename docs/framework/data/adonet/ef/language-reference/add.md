---
title: + (Aggiungere)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51769b02-a8f7-4177-9e99-bbd10e77092c
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: abd5921653e65c69da99a1aff60506aafd814278
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="-add"></a><span data-ttu-id="66d6f-102">+ (addizione)</span><span class="sxs-lookup"><span data-stu-id="66d6f-102">+ (Add)</span></span>
<span data-ttu-id="66d6f-103">Esegue l'addizione di due numeri.</span><span class="sxs-lookup"><span data-stu-id="66d6f-103">Adds two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66d6f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="66d6f-104">Syntax</span></span>  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="66d6f-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="66d6f-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="66d6f-106">Qualsiasi espressione valida con qualsiasi tipo di dati numerici.</span><span class="sxs-lookup"><span data-stu-id="66d6f-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="66d6f-107">Tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="66d6f-107">Result Types</span></span>  
 <span data-ttu-id="66d6f-108">Tipo di dati ottenuto della promozione implicita del tipo dei due argomenti.</span><span class="sxs-lookup"><span data-stu-id="66d6f-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="66d6f-109">Per ulteriori informazioni sulla promozione implicita del tipo, vedere [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="66d6f-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66d6f-110">Note</span><span class="sxs-lookup"><span data-stu-id="66d6f-110">Remarks</span></span>  
 <span data-ttu-id="66d6f-111">Per i tipi EDM.String, l'aggiunta è la concatenazione.</span><span class="sxs-lookup"><span data-stu-id="66d6f-111">For EDM.String types, addition is concatenation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66d6f-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="66d6f-112">Example</span></span>  
 <span data-ttu-id="66d6f-113">Nella query Entity SQL seguente viene usato l'operatore aritmetico + per sommare due numeri.</span><span class="sxs-lookup"><span data-stu-id="66d6f-113">The following Entity SQL query uses the + arithmetic operator to add two numbers.</span></span> <span data-ttu-id="66d6f-114">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="66d6f-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="66d6f-115">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="66d6f-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="66d6f-116">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="66d6f-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="66d6f-117">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="66d6f-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ADD](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#add)]  
  
## <a name="see-also"></a><span data-ttu-id="66d6f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66d6f-118">See Also</span></span>  
 [<span data-ttu-id="66d6f-119">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="66d6f-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="66d6f-120">Tipi di modello concettuale (CSDL)</span><span class="sxs-lookup"><span data-stu-id="66d6f-120">Conceptual Model Types (CSDL)</span></span>](http://msdn.microsoft.com/en-us/987b995f-e429-4569-9559-b4146744def4)
