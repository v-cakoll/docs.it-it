---
title: LIMIT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: c22ffede-0a52-44d1-99b9-4a91e651e1b9
ms.openlocfilehash: 275b22686c6c932b2a9e4b20973ac07e99d47e14
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319620"
---
# <a name="limit-entity-sql"></a><span data-ttu-id="18884-102">LIMIT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="18884-102">LIMIT (Entity SQL)</span></span>
<span data-ttu-id="18884-103">Il paging fisico può essere eseguito usando la sottoclausola LIMIT nella clausola ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="18884-103">Physical paging can be performed by using LIMIT sub-clause in ORDER BY clause.</span></span> <span data-ttu-id="18884-104">Non è possibile usare LIMIT separatamente dalla clausola ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="18884-104">LIMIT can not be used separately from ORDER BY clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18884-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="18884-105">Syntax</span></span>  
  
```sql  
[ LIMIT n ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="18884-106">argomenti</span><span class="sxs-lookup"><span data-stu-id="18884-106">Arguments</span></span>  
 `n`  
 <span data-ttu-id="18884-107">Numero di elementi che verranno selezionati.</span><span class="sxs-lookup"><span data-stu-id="18884-107">The number of items that will be selected.</span></span>  
  
 <span data-ttu-id="18884-108">Se una sottoclausola dell'espressione LIMIT è presente in una clausola ORDER BY, la query verrà ordinata in base alla specifica di ordinamento e il numero risultante di righe sarà limitato dall'espressione LIMIT.</span><span class="sxs-lookup"><span data-stu-id="18884-108">If a LIMIT expression sub-clause is present in an ORDER BY clause, the query will be sorted according to the sort specification and the resulting number of rows will be restricted by the LIMIT expression.</span></span> <span data-ttu-id="18884-109">LIMIT 5, ad esempio, limiterà il set di risultati a cinque istanze o righe.</span><span class="sxs-lookup"><span data-stu-id="18884-109">For instance, LIMIT 5 will restrict the result set to 5 instances or rows.</span></span> <span data-ttu-id="18884-110">Dal punto di vista funzionale, LIMIT è equivalente a TOP, con l'eccezione che per la presenza di LIMIT è necessaria la clausola ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="18884-110">LIMIT is functionally equivalent to TOP with the exception that LIMIT requires ORDER BY clause to be present.</span></span> <span data-ttu-id="18884-111">È possibile usare SKIP e LIMIT in modo indipendente insieme alla clausola ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="18884-111">SKIP and LIMIT can be used independently along with ORDER BY clause.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="18884-112">Una query Entity SQL viene considerata non valida se nella stessa espressione di query sono presenti il modificatore TOP e la sottoclausola SKIP.</span><span class="sxs-lookup"><span data-stu-id="18884-112">An Entity Sql query will be considered invalid if TOP modifier and SKIP sub-clause is present in the same query expression.</span></span> <span data-ttu-id="18884-113">È necessario riscrivere la query modificando l'espressione TOP nell'espressione LIMIT.</span><span class="sxs-lookup"><span data-stu-id="18884-113">The query should be rewritten by changing TOP expression to LIMIT expression.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18884-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="18884-114">Example</span></span>  
 <span data-ttu-id="18884-115">Nella query Entity SQL seguente viene usato l'operatore ORDER BY con LIMIT per specificare l'ordinamento usato per gli oggetti restituiti in un'istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="18884-115">The following Entity SQL query uses the ORDER BY operator with LIMIT to specify the sort order used on objects returned in a SELECT statement.</span></span> <span data-ttu-id="18884-116">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="18884-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="18884-117">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="18884-117">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="18884-118">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="18884-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="18884-119">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="18884-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#LIMIT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#limit)]  
  
## <a name="see-also"></a><span data-ttu-id="18884-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18884-120">See also</span></span>

- [<span data-ttu-id="18884-121">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="18884-121">ORDER BY</span></span>](order-by-entity-sql.md)
- <span data-ttu-id="18884-122">[Procedura: pagina tramite i risultati della query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="18884-122">[How to: Page Through Query Results](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))</span></span>
- [<span data-ttu-id="18884-123">Paging</span><span class="sxs-lookup"><span data-stu-id="18884-123">Paging</span></span>](paging-entity-sql.md)
- [<span data-ttu-id="18884-124">TOP</span><span class="sxs-lookup"><span data-stu-id="18884-124">TOP</span></span>](top-entity-sql.md)
