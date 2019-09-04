---
title: KEY (Entity SQL)
ms.date: 03/30/2017
ms.assetid: cbaa97a8-c89c-4460-8c74-00474695789f
ms.openlocfilehash: 44ab5352c3b2a94cb210c3de775d2347d2df7fe7
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250477"
---
# <a name="key-entity-sql"></a><span data-ttu-id="f9794-102">KEY (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f9794-102">KEY (Entity SQL)</span></span>
<span data-ttu-id="f9794-103">Estrae la chiave di un riferimento o di un'espressione di entità.</span><span class="sxs-lookup"><span data-stu-id="f9794-103">Extracts the key of a reference or of an entity expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9794-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f9794-104">Syntax</span></span>  
  
```  
KEY(createref_expression)  
```  
  
## <a name="remarks"></a><span data-ttu-id="f9794-105">Note</span><span class="sxs-lookup"><span data-stu-id="f9794-105">Remarks</span></span>  
 <span data-ttu-id="f9794-106">Una chiave di entità contiene nell'ordine corretto i valori di chiave relativi all'entità o al riferimento all'entità specificato.</span><span class="sxs-lookup"><span data-stu-id="f9794-106">An entity key contains the key values in the correct order of the specified entity or entity reference.</span></span> <span data-ttu-id="f9794-107">Poiché più set di entità possono essere basati sullo stesso tipo di entità, è possibile che venga visualizzata la stessa chiave in ogni set.</span><span class="sxs-lookup"><span data-stu-id="f9794-107">Because multiple entity sets can be based on the same type, the same key might appear in each entity set.</span></span> <span data-ttu-id="f9794-108">Per ottenere un riferimento univoco, usare `REF`.</span><span class="sxs-lookup"><span data-stu-id="f9794-108">To get a unique reference, use `REF`.</span></span> <span data-ttu-id="f9794-109">Il tipo restituito dell'operatore KEY è un tipo di riga che include un campo per ogni chiave dell'entità, nello stesso ordine.</span><span class="sxs-lookup"><span data-stu-id="f9794-109">The return type of the KEY operator is a row type that includes one field for each key of the entity, in the same order.</span></span>  
  
 <span data-ttu-id="f9794-110">Nell'esempio seguente all'operatore Key viene passato un riferimento all'entità BadOrder. Viene restituita la parte relativa alla chiave del riferimento in questione,</span><span class="sxs-lookup"><span data-stu-id="f9794-110">In the following example, the key operator is passed a reference to the BadOrder entity, and returns the key portion of that reference.</span></span> <span data-ttu-id="f9794-111">che in questo caso è un tipo di record con un campo esattamente corrispondente alla proprietà `Id` .</span><span class="sxs-lookup"><span data-stu-id="f9794-111">In this case, a record type with exactly one field corresponding to the `Id` property.</span></span>  
  
```  
select Key( CreateRef(LOB.BadOrders, row(o.Id)) )   
from LOB.Orders as o  
```  
  
## <a name="example"></a><span data-ttu-id="f9794-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="f9794-112">Example</span></span>  
 <span data-ttu-id="f9794-113">Nella query Entity SQL seguente viene usato l'operatore KEY per estrarre la parte relativa alla chiave di un'espressione con riferimento al tipo.</span><span class="sxs-lookup"><span data-stu-id="f9794-113">The following Entity SQL query uses the KEY operator to extract the key portion of an expression with type reference.</span></span> <span data-ttu-id="f9794-114">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="f9794-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="f9794-115">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f9794-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="f9794-116">Attenersi alla procedura descritta [in procedura: Eseguire una query che restituisce i risultati](../how-to-execute-a-query-that-returns-structuraltype-results.md)di StructuralType.</span><span class="sxs-lookup"><span data-stu-id="f9794-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="f9794-117">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="f9794-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#KEY](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#key)]  
  
## <a name="see-also"></a><span data-ttu-id="f9794-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9794-118">See also</span></span>

- [<span data-ttu-id="f9794-119">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="f9794-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="f9794-120">CREATEREF</span><span class="sxs-lookup"><span data-stu-id="f9794-120">CREATEREF</span></span>](createref-entity-sql.md)
- [<span data-ttu-id="f9794-121">REF</span><span class="sxs-lookup"><span data-stu-id="f9794-121">REF</span></span>](ref-entity-sql.md)
- [<span data-ttu-id="f9794-122">DEREF</span><span class="sxs-lookup"><span data-stu-id="f9794-122">DEREF</span></span>](deref-entity-sql.md)
