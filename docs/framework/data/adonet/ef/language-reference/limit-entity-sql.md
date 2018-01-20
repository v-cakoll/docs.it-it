---
title: LIMIT (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c22ffede-0a52-44d1-99b9-4a91e651e1b9
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c0b2a421b1187fcf88278b66f3225133330a3033
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="limit-entity-sql"></a><span data-ttu-id="0007b-102">LIMIT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="0007b-102">LIMIT (Entity SQL)</span></span>
<span data-ttu-id="0007b-103">Il paging fisico può essere eseguito usando la sottoclausola LIMIT nella clausola ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="0007b-103">Physical paging can be performed by using LIMIT sub-clause in ORDER BY clause.</span></span> <span data-ttu-id="0007b-104">Non è possibile usare LIMIT separatamente dalla clausola ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="0007b-104">LIMIT can not be used separately from ORDER BY clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0007b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0007b-105">Syntax</span></span>  
  
```  
[ LIMIT n ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="0007b-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="0007b-106">Arguments</span></span>  
 `n`  
 <span data-ttu-id="0007b-107">Numero di elementi che verranno selezionati.</span><span class="sxs-lookup"><span data-stu-id="0007b-107">The number of items that will be selected.</span></span>  
  
 <span data-ttu-id="0007b-108">Se una sottoclausola dell'espressione LIMIT è presente in una clausola ORDER BY, la query verrà ordinata in base alla specifica di ordinamento e il numero risultante di righe sarà limitato dall'espressione LIMIT.</span><span class="sxs-lookup"><span data-stu-id="0007b-108">If a LIMIT expression sub-clause is present in an ORDER BY clause, the query will be sorted according to the sort specification and the resulting number of rows will be restricted by the LIMIT expression.</span></span> <span data-ttu-id="0007b-109">LIMIT 5, ad esempio, limiterà il set di risultati a cinque istanze o righe.</span><span class="sxs-lookup"><span data-stu-id="0007b-109">For instance, LIMIT 5 will restrict the result set to 5 instances or rows.</span></span> <span data-ttu-id="0007b-110">Dal punto di vista funzionale, LIMIT è equivalente a TOP, con l'eccezione che per la presenza di LIMIT è necessaria la clausola ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="0007b-110">LIMIT is functionally equivalent to TOP with the exception that LIMIT requires ORDER BY clause to be present.</span></span> <span data-ttu-id="0007b-111">È possibile usare SKIP e LIMIT in modo indipendente insieme alla clausola ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="0007b-111">SKIP and LIMIT can be used independently along with ORDER BY clause.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0007b-112">Una query Entity SQL viene considerata non valida se nella stessa espressione di query sono presenti il modificatore TOP e la sottoclausola SKIP.</span><span class="sxs-lookup"><span data-stu-id="0007b-112">An Entity Sql query will be considered invalid if TOP modifier and SKIP sub-clause is present in the same query expression.</span></span> <span data-ttu-id="0007b-113">È necessario riscrivere la query modificando l'espressione TOP nell'espressione LIMIT.</span><span class="sxs-lookup"><span data-stu-id="0007b-113">The query should be rewritten by changing TOP expression to LIMIT expression.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0007b-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="0007b-114">Example</span></span>  
 <span data-ttu-id="0007b-115">Nella query Entity SQL seguente viene usato l'operatore ORDER BY con LIMIT per specificare l'ordinamento usato per gli oggetti restituiti in un'istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="0007b-115">The following Entity SQL query uses the ORDER BY operator with LIMIT to specify the sort order used on objects returned in a SELECT statement.</span></span> <span data-ttu-id="0007b-116">La query è basata sul modello Sales di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="0007b-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="0007b-117">Per compilare ed eseguire questa query, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0007b-117">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="0007b-118">Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="0007b-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="0007b-119">Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="0007b-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#LIMIT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#limit)]  
  
## <a name="see-also"></a><span data-ttu-id="0007b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0007b-120">See Also</span></span>  
 [<span data-ttu-id="0007b-121">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="0007b-121">ORDER BY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
 [<span data-ttu-id="0007b-122">Procedura: spostarsi tra Query i risultati</span><span class="sxs-lookup"><span data-stu-id="0007b-122">How to: Page Through Query Results</span></span>](http://msdn.microsoft.com/library/ffc0f920-e7de-42e0-9b12-ef356421d030)  
 [<span data-ttu-id="0007b-123">Paging</span><span class="sxs-lookup"><span data-stu-id="0007b-123">Paging</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)  
 [<span data-ttu-id="0007b-124">TOP</span><span class="sxs-lookup"><span data-stu-id="0007b-124">TOP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
