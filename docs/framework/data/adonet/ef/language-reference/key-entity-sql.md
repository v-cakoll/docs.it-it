---
title: KEY (Entity SQL)
ms.date: 03/30/2017
ms.assetid: cbaa97a8-c89c-4460-8c74-00474695789f
ms.openlocfilehash: 894a9d41aa3a14ad66b537433aa315823a299f95
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150169"
---
# <a name="key-entity-sql"></a><span data-ttu-id="43c50-102">KEY (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="43c50-102">KEY (Entity SQL)</span></span>
<span data-ttu-id="43c50-103">Estrae la chiave di un riferimento o di un'espressione di entità.</span><span class="sxs-lookup"><span data-stu-id="43c50-103">Extracts the key of a reference or of an entity expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43c50-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="43c50-104">Syntax</span></span>  
  
```sql  
KEY(createref_expression)  
```  
  
## <a name="remarks"></a><span data-ttu-id="43c50-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="43c50-105">Remarks</span></span>  
 <span data-ttu-id="43c50-106">Una chiave di entità contiene nell'ordine corretto i valori di chiave relativi all'entità o al riferimento all'entità specificato.</span><span class="sxs-lookup"><span data-stu-id="43c50-106">An entity key contains the key values in the correct order of the specified entity or entity reference.</span></span> <span data-ttu-id="43c50-107">Poiché più set di entità possono essere basati sullo stesso tipo di entità, è possibile che venga visualizzata la stessa chiave in ogni set.</span><span class="sxs-lookup"><span data-stu-id="43c50-107">Because multiple entity sets can be based on the same type, the same key might appear in each entity set.</span></span> <span data-ttu-id="43c50-108">Per ottenere un riferimento univoco, usare `REF`.</span><span class="sxs-lookup"><span data-stu-id="43c50-108">To get a unique reference, use `REF`.</span></span> <span data-ttu-id="43c50-109">Il tipo restituito dell'operatore KEY è un tipo di riga che include un campo per ogni chiave dell'entità, nello stesso ordine.</span><span class="sxs-lookup"><span data-stu-id="43c50-109">The return type of the KEY operator is a row type that includes one field for each key of the entity, in the same order.</span></span>  
  
 <span data-ttu-id="43c50-110">Nell'esempio seguente all'operatore Key viene passato un riferimento all'entità BadOrder. Viene restituita la parte relativa alla chiave del riferimento in questione,</span><span class="sxs-lookup"><span data-stu-id="43c50-110">In the following example, the key operator is passed a reference to the BadOrder entity, and returns the key portion of that reference.</span></span> <span data-ttu-id="43c50-111">che in questo caso è un tipo di record con un campo esattamente corrispondente alla proprietà `Id` .</span><span class="sxs-lookup"><span data-stu-id="43c50-111">In this case, a record type with exactly one field corresponding to the `Id` property.</span></span>  
  
```sql  
select Key( CreateRef(LOB.BadOrders, row(o.Id)) )
from LOB.Orders as o  
```  
  
## <a name="example"></a><span data-ttu-id="43c50-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="43c50-112">Example</span></span>  
 <span data-ttu-id="43c50-113">Nella query Entity SQL seguente viene usato l'operatore KEY per estrarre la parte relativa alla chiave di un'espressione con riferimento al tipo.</span><span class="sxs-lookup"><span data-stu-id="43c50-113">The following Entity SQL query uses the KEY operator to extract the key portion of an expression with type reference.</span></span> <span data-ttu-id="43c50-114">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="43c50-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="43c50-115">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="43c50-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="43c50-116">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="43c50-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="43c50-117">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="43c50-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#KEY](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#key)]  
  
## <a name="see-also"></a><span data-ttu-id="43c50-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43c50-118">See also</span></span>

- [<span data-ttu-id="43c50-119">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="43c50-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="43c50-120">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="43c50-120">CREATEREF</span></span>](createref-entity-sql.md)
- [<span data-ttu-id="43c50-121">Ref</span><span class="sxs-lookup"><span data-stu-id="43c50-121">REF</span></span>](ref-entity-sql.md)
- [<span data-ttu-id="43c50-122">DEREF</span><span class="sxs-lookup"><span data-stu-id="43c50-122">DEREF</span></span>](deref-entity-sql.md)
