---
title: USING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: 89306c8b4c317ebaba0d964869c4fe9e1028631a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762338"
---
# <a name="using-entity-sql"></a><span data-ttu-id="e54fb-102">USING (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e54fb-102">USING (Entity SQL)</span></span>
<span data-ttu-id="e54fb-103">Specifica gli spazi dei nomi usati in un'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="e54fb-103">Specifies namespaces used in a query expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e54fb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e54fb-104">Syntax</span></span>  
  
```  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="e54fb-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="e54fb-105">Arguments</span></span>  
 `alias`  
 <span data-ttu-id="e54fb-106">Specifica un alias più breve con cui qualificare uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="e54fb-106">Specifies a shorter alias to qualify a namespace with.</span></span>  
  
 `namespace`  
 <span data-ttu-id="e54fb-107">Qualsiasi spazio dei nomi valido.</span><span class="sxs-lookup"><span data-stu-id="e54fb-107">Any valid namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e54fb-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="e54fb-108">Example</span></span>  
 <span data-ttu-id="e54fb-109">Nella query Entity SQL seguente viene usato l'operatore USING per specificare gli spazi dei nomi usati in un'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="e54fb-109">The following Entity SQL query uses the USING operator to specify namespaces used in a query expression.</span></span> <span data-ttu-id="e54fb-110">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e54fb-110">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="e54fb-111">Attenersi alla procedura di [procedura: eseguire una Query che restituisce risultati di PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="e54fb-111">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="e54fb-112">Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="e54fb-112">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
```  
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a><span data-ttu-id="e54fb-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e54fb-113">See Also</span></span>  
 [<span data-ttu-id="e54fb-114">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="e54fb-114">Namespaces</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)  
 [<span data-ttu-id="e54fb-115">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e54fb-115">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
