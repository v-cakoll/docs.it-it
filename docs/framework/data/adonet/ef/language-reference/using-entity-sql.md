---
title: USING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: e14b7857a65898683939647c872c48d0b3fe458a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59297863"
---
# <a name="using-entity-sql"></a><span data-ttu-id="6bd97-102">USING (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6bd97-102">USING (Entity SQL)</span></span>
<span data-ttu-id="6bd97-103">Specifica gli spazi dei nomi usati in un'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="6bd97-103">Specifies namespaces used in a query expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bd97-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6bd97-104">Syntax</span></span>  
  
```  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="6bd97-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="6bd97-105">Arguments</span></span>  
 `alias`  
 <span data-ttu-id="6bd97-106">Specifica un alias più breve con cui qualificare uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="6bd97-106">Specifies a shorter alias to qualify a namespace with.</span></span>  
  
 `namespace`  
 <span data-ttu-id="6bd97-107">Qualsiasi spazio dei nomi valido.</span><span class="sxs-lookup"><span data-stu-id="6bd97-107">Any valid namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6bd97-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="6bd97-108">Example</span></span>  
 <span data-ttu-id="6bd97-109">Nella query Entity SQL seguente viene usato l'operatore USING per specificare gli spazi dei nomi usati in un'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="6bd97-109">The following Entity SQL query uses the USING operator to specify namespaces used in a query expression.</span></span> <span data-ttu-id="6bd97-110">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6bd97-110">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="6bd97-111">Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="6bd97-111">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="6bd97-112">Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="6bd97-112">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
```  
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a><span data-ttu-id="6bd97-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6bd97-113">See also</span></span>

- [<span data-ttu-id="6bd97-114">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="6bd97-114">Namespaces</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)
- [<span data-ttu-id="6bd97-115">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="6bd97-115">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
