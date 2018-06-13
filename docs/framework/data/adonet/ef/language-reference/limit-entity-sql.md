---
title: LIMIT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c22ffede-0a52-44d1-99b9-4a91e651e1b9
ms.openlocfilehash: b844c5a132d36a4ca9d660607bbfe0f39ceab718
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759634"
---
# <a name="limit-entity-sql"></a><span data-ttu-id="316b1-102">LIMIT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="316b1-102">LIMIT (Entity SQL)</span></span>
<span data-ttu-id="316b1-103">Il paging fisico può essere eseguito usando la sottoclausola LIMIT nella clausola ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="316b1-103">Physical paging can be performed by using LIMIT sub-clause in ORDER BY clause.</span></span> <span data-ttu-id="316b1-104">Non è possibile usare LIMIT separatamente dalla clausola ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="316b1-104">LIMIT can not be used separately from ORDER BY clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="316b1-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="316b1-105">Syntax</span></span>  
  
```  
[ LIMIT n ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="316b1-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="316b1-106">Arguments</span></span>  
 `n`  
 <span data-ttu-id="316b1-107">Numero di elementi che verranno selezionati.</span><span class="sxs-lookup"><span data-stu-id="316b1-107">The number of items that will be selected.</span></span>  
  
 <span data-ttu-id="316b1-108">Se una sottoclausola dell'espressione LIMIT è presente in una clausola ORDER BY, la query verrà ordinata in base alla specifica di ordinamento e il numero risultante di righe sarà limitato dall'espressione LIMIT.</span><span class="sxs-lookup"><span data-stu-id="316b1-108">If a LIMIT expression sub-clause is present in an ORDER BY clause, the query will be sorted according to the sort specification and the resulting number of rows will be restricted by the LIMIT expression.</span></span> <span data-ttu-id="316b1-109">LIMIT 5, ad esempio, limiterà il set di risultati a cinque istanze o righe.</span><span class="sxs-lookup"><span data-stu-id="316b1-109">For instance, LIMIT 5 will restrict the result set to 5 instances or rows.</span></span> <span data-ttu-id="316b1-110">Dal punto di vista funzionale, LIMIT è equivalente a TOP, con l'eccezione che per la presenza di LIMIT è necessaria la clausola ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="316b1-110">LIMIT is functionally equivalent to TOP with the exception that LIMIT requires ORDER BY clause to be present.</span></span> <span data-ttu-id="316b1-111">È possibile usare SKIP e LIMIT in modo indipendente insieme alla clausola ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="316b1-111">SKIP and LIMIT can be used independently along with ORDER BY clause.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="316b1-112">Una query Entity SQL viene considerata non valida se nella stessa espressione di query sono presenti il modificatore TOP e la sottoclausola SKIP.</span><span class="sxs-lookup"><span data-stu-id="316b1-112">An Entity Sql query will be considered invalid if TOP modifier and SKIP sub-clause is present in the same query expression.</span></span> <span data-ttu-id="316b1-113">È necessario riscrivere la query modificando l'espressione TOP nell'espressione LIMIT.</span><span class="sxs-lookup"><span data-stu-id="316b1-113">The query should be rewritten by changing TOP expression to LIMIT expression.</span></span>  
  
## <a name="example"></a><span data-ttu-id="316b1-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="316b1-114">Example</span></span>  
 <span data-ttu-id="316b1-115">Nella query Entity SQL seguente viene usato l'operatore ORDER BY con LIMIT per specificare l'ordinamento usato per gli oggetti restituiti in un'istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="316b1-115">The following Entity SQL query uses the ORDER BY operator with LIMIT to specify the sort order used on objects returned in a SELECT statement.</span></span> <span data-ttu-id="316b1-116">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="316b1-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="316b1-117">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="316b1-117">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="316b1-118">Seguire la procedura indicata in [Procedura: eseguire una query che restituisce risultati StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="316b1-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="316b1-119">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="316b1-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#LIMIT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#limit)]  
  
## <a name="see-also"></a><span data-ttu-id="316b1-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="316b1-120">See Also</span></span>  
 [<span data-ttu-id="316b1-121">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="316b1-121">ORDER BY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
 [<span data-ttu-id="316b1-122">Procedura: spostarsi Query tra i risultati</span><span class="sxs-lookup"><span data-stu-id="316b1-122">How to: Page Through Query Results</span></span>](http://msdn.microsoft.com/library/ffc0f920-e7de-42e0-9b12-ef356421d030)  
 [<span data-ttu-id="316b1-123">Paging</span><span class="sxs-lookup"><span data-stu-id="316b1-123">Paging</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)  
 [<span data-ttu-id="316b1-124">TOP</span><span class="sxs-lookup"><span data-stu-id="316b1-124">TOP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
