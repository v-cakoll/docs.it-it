---
title: Archiviare i risultati di una query in memoria
description: Come archiviare i risultati.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 5b863961-1750-4cf9-9607-acea5054d15a
ms.openlocfilehash: 86a9c2d464eac83cabb5faa68987ad580fc31248
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2017
---
# <a name="store-the-results-of-a-query-in-memory"></a><span data-ttu-id="67841-104">Archiviare i risultati di una query in memoria</span><span class="sxs-lookup"><span data-stu-id="67841-104">Store the results of a query in memory</span></span>

<span data-ttu-id="67841-105">Una query è fondamentalmente un set di istruzioni per il recupero e l'organizzazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="67841-105">A query is basically a set of instructions for how to retrieve and organize data.</span></span> <span data-ttu-id="67841-106">Le query vengono eseguite in modalità lazy poiché viene richiesto ogni elemento successivo nel risultato.</span><span class="sxs-lookup"><span data-stu-id="67841-106">Queries are executed lazily, as each subsequent item in the result is requested.</span></span> <span data-ttu-id="67841-107">Quando si usa `foreach` per scorrere i risultati, gli elementi vengono restituiti quando ne viene eseguito l'accesso.</span><span class="sxs-lookup"><span data-stu-id="67841-107">When you use `foreach` to iterate the results, items are returned as accessed.</span></span> <span data-ttu-id="67841-108">Per valutare una query e archiviare i risultati senza eseguire un ciclo di `foreach`, è sufficiente chiamare uno dei seguenti metodi sulla variabile di query:</span><span class="sxs-lookup"><span data-stu-id="67841-108">To evaluate a query and store its results without executing a `foreach` loop, just call one of the following methods on the query variable:</span></span>  
  
-   <xref:System.Linq.Enumerable.ToList%2A>  
  
-   <xref:System.Linq.Enumerable.ToArray%2A>  
  
-   <xref:System.Linq.Enumerable.ToDictionary%2A>  
  
-   <xref:System.Linq.Enumerable.ToLookup%2A>  
  
 <span data-ttu-id="67841-109">Quando si archiviano i risultati della query, assegnare l'oggetto Collection restituito a una nuova variabile, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="67841-109">We recommend that when you store the query results, you assign the returned collection object to a new variable as shown in the following example:</span></span>  
  
## <a name="example"></a><span data-ttu-id="67841-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="67841-110">Example</span></span>  
 [!code-csharp[csProgGuideLINQ#25](../../../samples/snippets/csharp/concepts/linq/how-to-store-the-results-of-a-query-in-memory_1.cs)]  
  

## <a name="see-also"></a><span data-ttu-id="67841-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67841-111">See Also</span></span>  
 [<span data-ttu-id="67841-112">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="67841-112">LINQ Query Expressions</span></span>](index.md)
