---
title: Esecuzione e locale
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ee50e943-9349-4c84-ab1c-c35d3ada1a9c
ms.openlocfilehash: 9488cb4c15c2e0646d91bdba36e7d4e2be2efbbd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33360047"
---
# <a name="remote-vs-local-execution"></a><span data-ttu-id="a86b0-102">Esecuzione e locale</span><span class="sxs-lookup"><span data-stu-id="a86b0-102">Remote vs. Local Execution</span></span>
<span data-ttu-id="a86b0-103">È possibile scegliere di eseguire le query in modalità remota, dove il motore di database esegue la query sul database, oppure localmente, dove [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] esegue la query sulla cache locale.</span><span class="sxs-lookup"><span data-stu-id="a86b0-103">You can decide to execute your queries either remotely (that is, the database engine executes the query against the database) or locally ([!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] executes the query against a local cache).</span></span>  
  
## <a name="remote-execution"></a><span data-ttu-id="a86b0-104">Esecuzione remota</span><span class="sxs-lookup"><span data-stu-id="a86b0-104">Remote Execution</span></span>  
 <span data-ttu-id="a86b0-105">Si consideri la query riportata di seguito:</span><span class="sxs-lookup"><span data-stu-id="a86b0-105">Consider the following query:</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#7)]
 [!code-vb[DLinqQueryConcepts#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#7)]  
  
 <span data-ttu-id="a86b0-106">Se nel database sono presenti migliaia di righe di ordini, non è opportuno recuperarli tutti per elaborare un piccolo subset.</span><span class="sxs-lookup"><span data-stu-id="a86b0-106">If your database has thousands of rows of orders, you do not want to retrieve them all to process a small subset.</span></span> <span data-ttu-id="a86b0-107">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] la classe <xref:System.Data.Linq.EntitySet%601> implementa l'interfaccia <xref:System.Linq.IQueryable>.</span><span class="sxs-lookup"><span data-stu-id="a86b0-107">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Data.Linq.EntitySet%601> class implements the <xref:System.Linq.IQueryable> interface.</span></span> <span data-ttu-id="a86b0-108">Questo approccio assicura che tali query possano essere eseguite in modalità remota.</span><span class="sxs-lookup"><span data-stu-id="a86b0-108">This approach makes sure that such queries can be executed remotely.</span></span> <span data-ttu-id="a86b0-109">Questa tecnica offre due vantaggi principali:</span><span class="sxs-lookup"><span data-stu-id="a86b0-109">Two major benefits flow from this technique:</span></span>  
  
-   <span data-ttu-id="a86b0-110">I dati non necessari non vengono recuperati.</span><span class="sxs-lookup"><span data-stu-id="a86b0-110">Unnecessary data is not retrieved.</span></span>  
  
-   <span data-ttu-id="a86b0-111">Una query eseguita dal motore di database è spesso più efficiente grazie agli indici del database.</span><span class="sxs-lookup"><span data-stu-id="a86b0-111">A query executed by the database engine is often more efficient because of the database indexes.</span></span>  
  
## <a name="local-execution"></a><span data-ttu-id="a86b0-112">e locale</span><span class="sxs-lookup"><span data-stu-id="a86b0-112">Local Execution</span></span>  
 <span data-ttu-id="a86b0-113">In altre situazioni può essere necessario disporre del set completo di entità correlate nella cache locale.</span><span class="sxs-lookup"><span data-stu-id="a86b0-113">In other situations, you might want to have the complete set of related entities in the local cache.</span></span> <span data-ttu-id="a86b0-114">A questo scopo <xref:System.Data.Linq.EntitySet%601> fornisce il metodo <xref:System.Data.Linq.EntitySet%601.Load%2A> per caricare in modo esplicito tutti i membri di <xref:System.Data.Linq.EntitySet%601>.</span><span class="sxs-lookup"><span data-stu-id="a86b0-114">For this purpose, <xref:System.Data.Linq.EntitySet%601> provides the <xref:System.Data.Linq.EntitySet%601.Load%2A> method to explicitly load all the members of the <xref:System.Data.Linq.EntitySet%601>.</span></span>  
  
 <span data-ttu-id="a86b0-115">Se <xref:System.Data.Linq.EntitySet%601> è già caricato, le query successive vengono eseguite localmente.</span><span class="sxs-lookup"><span data-stu-id="a86b0-115">If an <xref:System.Data.Linq.EntitySet%601> is already loaded, subsequent queries are executed locally.</span></span> <span data-ttu-id="a86b0-116">Questo approccio risulta utile in due modi:</span><span class="sxs-lookup"><span data-stu-id="a86b0-116">This approach helps in two ways:</span></span>  
  
-   <span data-ttu-id="a86b0-117">Se il set completo deve essere usato localmente o più volte, è possibile evitare l'esecuzione di query remote e le latenze che ne derivano.</span><span class="sxs-lookup"><span data-stu-id="a86b0-117">If the complete set must be used locally or multiple times, you can avoid remote queries and associated latencies.</span></span>  
  
-   <span data-ttu-id="a86b0-118">L'entità può essere serializzata come un'entità completa.</span><span class="sxs-lookup"><span data-stu-id="a86b0-118">The entity can be serialized as a complete entity.</span></span>  
  
 <span data-ttu-id="a86b0-119">Il frammento di codice seguente illustra come è possibile ottenere l'esecuzione locale:</span><span class="sxs-lookup"><span data-stu-id="a86b0-119">The following code fragment illustrates how local execution can be obtained:</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#8)]
 [!code-vb[DLinqQueryConcepts#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#8)]  
  
## <a name="comparison"></a><span data-ttu-id="a86b0-120">Confronto</span><span class="sxs-lookup"><span data-stu-id="a86b0-120">Comparison</span></span>  
 <span data-ttu-id="a86b0-121">Queste due funzionalità consentono di ottenere una potente combinazione di opzioni: l'esecuzione remota per le raccolte di grandi dimensioni e l'esecuzione locale per le piccole raccolte o dove è necessario disporre della raccolta completa.</span><span class="sxs-lookup"><span data-stu-id="a86b0-121">These two capabilities provide a powerful combination of options: remote execution for large collections and local execution for small collections or where the complete collection is needed.</span></span> <span data-ttu-id="a86b0-122">L'esecuzione remota viene implementata tramite <xref:System.Linq.IQueryable>, mentre l'esecuzione locale viene implementata su una raccolta <xref:System.Collections.Generic.IEnumerable%601> in memoria.</span><span class="sxs-lookup"><span data-stu-id="a86b0-122">You implement remote execution through <xref:System.Linq.IQueryable>, and local execution against an in-memory <xref:System.Collections.Generic.IEnumerable%601> collection.</span></span> <span data-ttu-id="a86b0-123">Per forzare l'esecuzione locale (ovvero, <xref:System.Collections.Generic.IEnumerable%601>), vedere [convertire un tipo in un IEnumerable generico](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-type-to-a-generic-ienumerable.md).</span><span class="sxs-lookup"><span data-stu-id="a86b0-123">To force local execution (that is, <xref:System.Collections.Generic.IEnumerable%601>), see [Convert a Type to a Generic IEnumerable](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-type-to-a-generic-ienumerable.md).</span></span>  
  
### <a name="queries-against-unordered-sets"></a><span data-ttu-id="a86b0-124">Query su set non ordinati</span><span class="sxs-lookup"><span data-stu-id="a86b0-124">Queries Against Unordered Sets</span></span>  
 <span data-ttu-id="a86b0-125">Notare l'importante differenza tra una raccolta locale che implementa <xref:System.Collections.Generic.List%601> e una raccolta che fornisce query remote eseguite su *insiemi non ordinati* in un database relazionale.</span><span class="sxs-lookup"><span data-stu-id="a86b0-125">Note the important difference between a local collection that implements <xref:System.Collections.Generic.List%601> and a collection that provides remote queries executed against *unordered sets* in a relational database.</span></span> <span data-ttu-id="a86b0-126">I metodi <xref:System.Collections.Generic.List%601>, ad esempio quelli che usano valori di indice, richiedono la semantica di elenco che in genere non può essere ottenuta tramite una query remota su un set non ordinato.</span><span class="sxs-lookup"><span data-stu-id="a86b0-126"><xref:System.Collections.Generic.List%601> methods such as those that use index values require list semantics, which typically cannot be obtained through a remote query against an unordered set.</span></span> <span data-ttu-id="a86b0-127">Per questo motivo, tali metodi caricano in modo implicito <xref:System.Data.Linq.EntitySet%601> per consentire l'esecuzione locale.</span><span class="sxs-lookup"><span data-stu-id="a86b0-127">For this reason, such methods implicitly load the <xref:System.Data.Linq.EntitySet%601> to allow local execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a86b0-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a86b0-128">See Also</span></span>  
 [<span data-ttu-id="a86b0-129">Concetti relativi alle query</span><span class="sxs-lookup"><span data-stu-id="a86b0-129">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
