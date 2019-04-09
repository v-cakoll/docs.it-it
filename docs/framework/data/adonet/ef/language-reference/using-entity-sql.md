---
title: USING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: 6a5b374bc253cb2deb7a9e1de942c32d8e8bbfcf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168025"
---
# <a name="using-entity-sql"></a><span data-ttu-id="5631d-102">USING (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5631d-102">USING (Entity SQL)</span></span>
<span data-ttu-id="5631d-103">Specifica gli spazi dei nomi usati in un'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="5631d-103">Specifies namespaces used in a query expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5631d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5631d-104">Syntax</span></span>  
  
```  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="5631d-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="5631d-105">Arguments</span></span>  
 `alias`  
 <span data-ttu-id="5631d-106">Specifica un alias più breve con cui qualificare uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="5631d-106">Specifies a shorter alias to qualify a namespace with.</span></span>  
  
 `namespace`  
 <span data-ttu-id="5631d-107">Qualsiasi spazio dei nomi valido.</span><span class="sxs-lookup"><span data-stu-id="5631d-107">Any valid namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5631d-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="5631d-108">Example</span></span>  
 <span data-ttu-id="5631d-109">Nella query Entity SQL seguente viene usato l'operatore USING per specificare gli spazi dei nomi usati in un'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="5631d-109">The following Entity SQL query uses the USING operator to specify namespaces used in a query expression.</span></span> <span data-ttu-id="5631d-110">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5631d-110">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="5631d-111">Attenersi alla procedura di [come: Eseguire una Query che restituisce risultati PrimitiveType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="5631d-111">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="5631d-112">Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="5631d-112">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
```  
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a><span data-ttu-id="5631d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5631d-113">See also</span></span>

- [<span data-ttu-id="5631d-114">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="5631d-114">Namespaces</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)
- [<span data-ttu-id="5631d-115">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="5631d-115">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
