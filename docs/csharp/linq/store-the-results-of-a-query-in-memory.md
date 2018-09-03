---
title: Archiviare i risultati di una query in memoria
description: Come archiviare i risultati.
ms.date: 11/30/2016
ms.assetid: 5b863961-1750-4cf9-9607-acea5054d15a
ms.openlocfilehash: 98a300b2c11eb037ed4ce34caea2673a4e0f8e6b
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2018
ms.locfileid: "43258082"
---
# <a name="store-the-results-of-a-query-in-memory"></a><span data-ttu-id="bef8e-103">Archiviare i risultati di una query in memoria</span><span class="sxs-lookup"><span data-stu-id="bef8e-103">Store the results of a query in memory</span></span>

<span data-ttu-id="bef8e-104">Una query è fondamentalmente un set di istruzioni per il recupero e l'organizzazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="bef8e-104">A query is basically a set of instructions for how to retrieve and organize data.</span></span> <span data-ttu-id="bef8e-105">Le query vengono eseguite in modalità lazy poiché viene richiesto ogni elemento successivo nel risultato.</span><span class="sxs-lookup"><span data-stu-id="bef8e-105">Queries are executed lazily, as each subsequent item in the result is requested.</span></span> <span data-ttu-id="bef8e-106">Quando si usa `foreach` per scorrere i risultati, gli elementi vengono restituiti quando ne viene eseguito l'accesso.</span><span class="sxs-lookup"><span data-stu-id="bef8e-106">When you use `foreach` to iterate the results, items are returned as accessed.</span></span> <span data-ttu-id="bef8e-107">Per valutare una query e archiviare i risultati senza eseguire un ciclo di `foreach`, è sufficiente chiamare uno dei seguenti metodi sulla variabile di query:</span><span class="sxs-lookup"><span data-stu-id="bef8e-107">To evaluate a query and store its results without executing a `foreach` loop, just call one of the following methods on the query variable:</span></span>

- <xref:System.Linq.Enumerable.ToList%2A>

- <xref:System.Linq.Enumerable.ToArray%2A>

- <xref:System.Linq.Enumerable.ToDictionary%2A>

- <xref:System.Linq.Enumerable.ToLookup%2A>

 <span data-ttu-id="bef8e-108">Quando si archiviano i risultati della query, assegnare l'oggetto Collection restituito a una nuova variabile, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="bef8e-108">We recommend that when you store the query results, you assign the returned collection object to a new variable as shown in the following example:</span></span>

## <a name="example"></a><span data-ttu-id="bef8e-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="bef8e-109">Example</span></span>

[!code-csharp[csProgGuideLINQ#25](~/samples/snippets/csharp/concepts/linq/how-to-store-the-results-of-a-query-in-memory_1.cs)]

## <a name="see-also"></a><span data-ttu-id="bef8e-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bef8e-110">See also</span></span>

- [<span data-ttu-id="bef8e-111">LINQ (Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="bef8e-111">Language Integrated Query (LINQ)</span></span>](index.md)