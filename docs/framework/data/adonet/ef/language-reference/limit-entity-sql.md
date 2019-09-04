---
title: LIMIT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c22ffede-0a52-44d1-99b9-4a91e651e1b9
ms.openlocfilehash: 432dfe2c8b2b87daf885be6de4da9bbeaaa37638
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250437"
---
# <a name="limit-entity-sql"></a><span data-ttu-id="4f87a-102">LIMIT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="4f87a-102">LIMIT (Entity SQL)</span></span>
<span data-ttu-id="4f87a-103">Il paging fisico può essere eseguito usando la sottoclausola LIMIT nella clausola ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="4f87a-103">Physical paging can be performed by using LIMIT sub-clause in ORDER BY clause.</span></span> <span data-ttu-id="4f87a-104">Non è possibile usare LIMIT separatamente dalla clausola ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="4f87a-104">LIMIT can not be used separately from ORDER BY clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f87a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4f87a-105">Syntax</span></span>  
  
```  
[ LIMIT n ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="4f87a-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="4f87a-106">Arguments</span></span>  
 `n`  
 <span data-ttu-id="4f87a-107">Numero di elementi che verranno selezionati.</span><span class="sxs-lookup"><span data-stu-id="4f87a-107">The number of items that will be selected.</span></span>  
  
 <span data-ttu-id="4f87a-108">Se una sottoclausola dell'espressione LIMIT è presente in una clausola ORDER BY, la query verrà ordinata in base alla specifica di ordinamento e il numero risultante di righe sarà limitato dall'espressione LIMIT.</span><span class="sxs-lookup"><span data-stu-id="4f87a-108">If a LIMIT expression sub-clause is present in an ORDER BY clause, the query will be sorted according to the sort specification and the resulting number of rows will be restricted by the LIMIT expression.</span></span> <span data-ttu-id="4f87a-109">LIMIT 5, ad esempio, limiterà il set di risultati a cinque istanze o righe.</span><span class="sxs-lookup"><span data-stu-id="4f87a-109">For instance, LIMIT 5 will restrict the result set to 5 instances or rows.</span></span> <span data-ttu-id="4f87a-110">Dal punto di vista funzionale, LIMIT è equivalente a TOP, con l'eccezione che per la presenza di LIMIT è necessaria la clausola ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="4f87a-110">LIMIT is functionally equivalent to TOP with the exception that LIMIT requires ORDER BY clause to be present.</span></span> <span data-ttu-id="4f87a-111">È possibile usare SKIP e LIMIT in modo indipendente insieme alla clausola ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="4f87a-111">SKIP and LIMIT can be used independently along with ORDER BY clause.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4f87a-112">Una query Entity SQL viene considerata non valida se nella stessa espressione di query sono presenti il modificatore TOP e la sottoclausola SKIP.</span><span class="sxs-lookup"><span data-stu-id="4f87a-112">An Entity Sql query will be considered invalid if TOP modifier and SKIP sub-clause is present in the same query expression.</span></span> <span data-ttu-id="4f87a-113">È necessario riscrivere la query modificando l'espressione TOP nell'espressione LIMIT.</span><span class="sxs-lookup"><span data-stu-id="4f87a-113">The query should be rewritten by changing TOP expression to LIMIT expression.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f87a-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="4f87a-114">Example</span></span>  
 <span data-ttu-id="4f87a-115">Nella query Entity SQL seguente viene usato l'operatore ORDER BY con LIMIT per specificare l'ordinamento usato per gli oggetti restituiti in un'istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="4f87a-115">The following Entity SQL query uses the ORDER BY operator with LIMIT to specify the sort order used on objects returned in a SELECT statement.</span></span> <span data-ttu-id="4f87a-116">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="4f87a-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="4f87a-117">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f87a-117">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="4f87a-118">Attenersi alla procedura descritta [in procedura: Eseguire una query che restituisce i risultati](../how-to-execute-a-query-that-returns-structuraltype-results.md)di StructuralType.</span><span class="sxs-lookup"><span data-stu-id="4f87a-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="4f87a-119">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="4f87a-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#LIMIT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#limit)]  
  
## <a name="see-also"></a><span data-ttu-id="4f87a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f87a-120">See also</span></span>

- [<span data-ttu-id="4f87a-121">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="4f87a-121">ORDER BY</span></span>](order-by-entity-sql.md)
- <span data-ttu-id="4f87a-122">[Procedura: Pagina tramite i risultati della query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="4f87a-122">[How to: Page Through Query Results](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span></span>
- [<span data-ttu-id="4f87a-123">Paging</span><span class="sxs-lookup"><span data-stu-id="4f87a-123">Paging</span></span>](paging-entity-sql.md)
- [<span data-ttu-id="4f87a-124">TOP</span><span class="sxs-lookup"><span data-stu-id="4f87a-124">TOP</span></span>](top-entity-sql.md)
