---
title: FLATTEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1a670c63-0a29-4738-80e6-101f66af05c3
ms.openlocfilehash: 327a20bbc53566846e7d828f511bcd1d25cc5504
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250962"
---
# <a name="flatten-entity-sql"></a><span data-ttu-id="b4db1-102">FLATTEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b4db1-102">FLATTEN (Entity SQL)</span></span>
<span data-ttu-id="b4db1-103">Converte una raccolta di raccolte in una raccolta bidimensionale.</span><span class="sxs-lookup"><span data-stu-id="b4db1-103">Converts a collection of collections into a flattened collection.</span></span> <span data-ttu-id="b4db1-104">La nuova raccolta contiene tutti gli stessi elementi di quella vecchia, ma senza una struttura annidata.</span><span class="sxs-lookup"><span data-stu-id="b4db1-104">The new collection contains all the same elements as the old collection, but without a nested structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4db1-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b4db1-105">Syntax</span></span>  
  
```  
FLATTEN ( collection )  
```  
  
## <a name="arguments"></a><span data-ttu-id="b4db1-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="b4db1-106">Arguments</span></span>  
 `collection`  
 <span data-ttu-id="b4db1-107">Qualsiasi espressione valida che restituisce una raccolta di valori da inserire in un'unica raccolta bidimensionale.</span><span class="sxs-lookup"><span data-stu-id="b4db1-107">Any valid expression that returns a collection of value collections to flatten into a single collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4db1-108">Note</span><span class="sxs-lookup"><span data-stu-id="b4db1-108">Remarks</span></span>  
 <span data-ttu-id="b4db1-109">`FLATTEN` è uno degli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b4db1-109">`FLATTEN` is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="b4db1-110">Tutti gli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vengono valutati da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="b4db1-110">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="b4db1-111">Vedere [ad eccezione](except-entity-sql.md) delle informazioni di precedenza [!INCLUDE[esql](../../../../../../includes/esql-md.md)] per gli operatori sui set.</span><span class="sxs-lookup"><span data-stu-id="b4db1-111">See [EXCEPT](except-entity-sql.md) for precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4db1-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="b4db1-112">Example</span></span>  
 <span data-ttu-id="b4db1-113">Nella query Entity SQL seguente viene usato l'operatore `FLATTEN` per convertire una raccolta di raccolte in una raccolta bidimensionale.</span><span class="sxs-lookup"><span data-stu-id="b4db1-113">The following Entity SQL query uses the `FLATTEN` operator to convert a collection of collections into a flattened collection.</span></span> <span data-ttu-id="b4db1-114">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b4db1-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="b4db1-115">Attenersi alla procedura descritta [in procedura: Eseguire una query che restituisce i risultati](../how-to-execute-a-query-that-returns-structuraltype-results.md)di StructuralType.</span><span class="sxs-lookup"><span data-stu-id="b4db1-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="b4db1-116">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="b4db1-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#FLATTEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#flatten)]  
  
## <a name="see-also"></a><span data-ttu-id="b4db1-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4db1-117">See also</span></span>

- [<span data-ttu-id="b4db1-118">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="b4db1-118">Entity SQL Reference</span></span>](entity-sql-reference.md)
