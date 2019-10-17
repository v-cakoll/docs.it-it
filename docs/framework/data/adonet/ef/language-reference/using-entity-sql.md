---
title: USING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: 0bcd4a2140a04fa0ecbfa7eee450ed029f278286
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319211"
---
# <a name="using-entity-sql"></a><span data-ttu-id="b46c3-102">USING (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b46c3-102">USING (Entity SQL)</span></span>
<span data-ttu-id="b46c3-103">Specifica gli spazi dei nomi usati in un'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="b46c3-103">Specifies namespaces used in a query expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b46c3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b46c3-104">Syntax</span></span>  
  
```sql  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="b46c3-105">argomenti</span><span class="sxs-lookup"><span data-stu-id="b46c3-105">Arguments</span></span>  
 `alias`  
 <span data-ttu-id="b46c3-106">Specifica un alias più breve con cui qualificare uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b46c3-106">Specifies a shorter alias to qualify a namespace with.</span></span>  
  
 `namespace`  
 <span data-ttu-id="b46c3-107">Qualsiasi spazio dei nomi valido.</span><span class="sxs-lookup"><span data-stu-id="b46c3-107">Any valid namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b46c3-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="b46c3-108">Example</span></span>  
 <span data-ttu-id="b46c3-109">Nella query Entity SQL seguente viene usato l'operatore USING per specificare gli spazi dei nomi usati in un'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="b46c3-109">The following Entity SQL query uses the USING operator to specify namespaces used in a query expression.</span></span> <span data-ttu-id="b46c3-110">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b46c3-110">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="b46c3-111">Attenersi alla procedura descritta in [procedura: eseguire una query che restituisce i risultati di PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="b46c3-111">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="b46c3-112">Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="b46c3-112">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
```csharp
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a><span data-ttu-id="b46c3-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b46c3-113">See also</span></span>

- [<span data-ttu-id="b46c3-114">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="b46c3-114">Namespaces</span></span>](namespaces-entity-sql.md)
- [<span data-ttu-id="b46c3-115">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="b46c3-115">Entity SQL Reference</span></span>](entity-sql-reference.md)
