---
title: HAVING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b5d52d97-8372-4335-beac-2d0b79dc3707
ms.openlocfilehash: 76a63140668fb1f41cf9e6f901d9a43240a1d098
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936076"
---
# <a name="having-entity-sql"></a><span data-ttu-id="3b4c0-102">HAVING (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="3b4c0-102">HAVING (Entity SQL)</span></span>
<span data-ttu-id="3b4c0-103">Specifica una condizione di ricerca per un gruppo o un'aggregazione.</span><span class="sxs-lookup"><span data-stu-id="3b4c0-103">Specifies a search condition for a group or an aggregate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b4c0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3b4c0-104">Syntax</span></span>  
  
```  
[ HAVING search_condition ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="3b4c0-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="3b4c0-105">Arguments</span></span>  
 `search_condition`  
 <span data-ttu-id="3b4c0-106">Specifica la condizione di ricerca che il gruppo o l'aggregazione deve soddisfare.</span><span class="sxs-lookup"><span data-stu-id="3b4c0-106">Specifies the search condition for the group or the aggregate to meet.</span></span> <span data-ttu-id="3b4c0-107">Se viene usata assieme alla clausola GROUP BY ALL, la clausola HAVING è prioritaria rispetto a ALL.</span><span class="sxs-lookup"><span data-stu-id="3b4c0-107">When HAVING is used with GROUP BY ALL, the HAVING clause overrides ALL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b4c0-108">Note</span><span class="sxs-lookup"><span data-stu-id="3b4c0-108">Remarks</span></span>  
 <span data-ttu-id="3b4c0-109">La clausola HAVING viene usata per specificare una condizione di filtro aggiuntiva sul risultato di un raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="3b4c0-109">The HAVING clause is used to specify an additional filtering condition on the result of a grouping.</span></span> <span data-ttu-id="3b4c0-110">Se non viene specificata alcuna clausola GROUP BY nell'espressione di query, viene presupposto un gruppo con singolo set implicito.</span><span class="sxs-lookup"><span data-stu-id="3b4c0-110">If no GROUP BY clause is specified in the query expression, an implicit single-set group is assumed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3b4c0-111">HAVING può essere utilizzato solo con l'istruzione [Select](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="3b4c0-111">HAVING can be used only with the [SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md) statement.</span></span> <span data-ttu-id="3b4c0-112">Se non si usa [Group by](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) , la clausola HAVING si comporta come una clausola WHERE.</span><span class="sxs-lookup"><span data-stu-id="3b4c0-112">When [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) is not used, HAVING behaves like a WHERE clause.</span></span>  
  
 <span data-ttu-id="3b4c0-113">La clausola HAVING funziona come la clausola WHERE eccetto per il fatto che viene applicata dopo l'operazione GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="3b4c0-113">The HAVING clause works like the WHERE clause except that it is applied after the GROUP BY operation.</span></span> <span data-ttu-id="3b4c0-114">Questo significa che la clausola HAVING può fare riferimento solo alle aggregazioni e agli alias di raggruppamento, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="3b4c0-114">This means that the HAVING clause can only make references to grouping aliases and aggregates, as illustrated in the following example.</span></span>  
  
```  
SELECT Name, SUM(o.Price * o.Quantity) AS Total FROM orderLines AS o GROUP BY o.Product AS Name  
HAVING SUM(o.Quantity) > 1  
```  
  
 <span data-ttu-id="3b4c0-115">L'esempio precedente consente di limitare i gruppi esclusivamente a quelli che includono più di un prodotto.</span><span class="sxs-lookup"><span data-stu-id="3b4c0-115">The previous restricts the groups to only those that include more than one product.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b4c0-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="3b4c0-116">Example</span></span>  
 <span data-ttu-id="3b4c0-117">Nella query Entity SQL seguente vengono usati gli operatori HAVING e GROUP BY per specificare una condizione di ricerca per un gruppo o un'aggregazione.</span><span class="sxs-lookup"><span data-stu-id="3b4c0-117">The following Entity SQL query uses the HAVING and GROUP BY operators to specify a search condition for a group or an aggregate.</span></span> <span data-ttu-id="3b4c0-118">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="3b4c0-118">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="3b4c0-119">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3b4c0-119">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="3b4c0-120">Attenersi alla procedura descritta [in procedura: Eseguire una query che restituisce i risultati](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)di PrimitiveType.</span><span class="sxs-lookup"><span data-stu-id="3b4c0-120">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="3b4c0-121">Passare la query seguente come argomento al metodo `ExecutePrimitiveTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="3b4c0-121">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#HAVING](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#having)]  
  
## <a name="see-also"></a><span data-ttu-id="3b4c0-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b4c0-122">See also</span></span>

- [<span data-ttu-id="3b4c0-123">Riferimento a Entity SQL</span><span class="sxs-lookup"><span data-stu-id="3b4c0-123">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="3b4c0-124">Espressioni di query</span><span class="sxs-lookup"><span data-stu-id="3b4c0-124">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
