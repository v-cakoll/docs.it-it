---
title: FLATTEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1a670c63-0a29-4738-80e6-101f66af05c3
ms.openlocfilehash: 84b846e3db86c664bc42363f3d983a1001f5c318
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833811"
---
# <a name="flatten-entity-sql"></a><span data-ttu-id="afa00-102">FLATTEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="afa00-102">FLATTEN (Entity SQL)</span></span>
<span data-ttu-id="afa00-103">Converte una raccolta di raccolte in una raccolta bidimensionale.</span><span class="sxs-lookup"><span data-stu-id="afa00-103">Converts a collection of collections into a flattened collection.</span></span> <span data-ttu-id="afa00-104">La nuova raccolta contiene tutti gli stessi elementi di quella vecchia, ma senza una struttura annidata.</span><span class="sxs-lookup"><span data-stu-id="afa00-104">The new collection contains all the same elements as the old collection, but without a nested structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afa00-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="afa00-105">Syntax</span></span>  
  
```sql  
FLATTEN ( collection )  
```  
  
## <a name="arguments"></a><span data-ttu-id="afa00-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="afa00-106">Arguments</span></span>  
 `collection`  
 <span data-ttu-id="afa00-107">Qualsiasi espressione valida che restituisce una raccolta di valori da inserire in un'unica raccolta bidimensionale.</span><span class="sxs-lookup"><span data-stu-id="afa00-107">Any valid expression that returns a collection of value collections to flatten into a single collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="afa00-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="afa00-108">Remarks</span></span>  
 <span data-ttu-id="afa00-109">`FLATTEN` è uno degli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="afa00-109">`FLATTEN` is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="afa00-110">Tutti gli operatori sui set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vengono valutati da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="afa00-110">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="afa00-111">Vedere [ad eccezione](except-entity-sql.md) delle informazioni di precedenza per gli operatori set di [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="afa00-111">See [EXCEPT](except-entity-sql.md) for precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="afa00-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="afa00-112">Example</span></span>  
 <span data-ttu-id="afa00-113">Nella query Entity SQL seguente viene usato l'operatore `FLATTEN` per convertire una raccolta di raccolte in una raccolta bidimensionale.</span><span class="sxs-lookup"><span data-stu-id="afa00-113">The following Entity SQL query uses the `FLATTEN` operator to convert a collection of collections into a flattened collection.</span></span> <span data-ttu-id="afa00-114">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="afa00-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="afa00-115">Seguire la procedura indicata in [Procedura: eseguire una query che restituisce risultati StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="afa00-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="afa00-116">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="afa00-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#FLATTEN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#flatten)]  
  
## <a name="see-also"></a><span data-ttu-id="afa00-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="afa00-117">See also</span></span>

- [<span data-ttu-id="afa00-118">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="afa00-118">Entity SQL Reference</span></span>](entity-sql-reference.md)
