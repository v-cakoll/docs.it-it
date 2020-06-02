---
title: Creare un pool di oggetti usando un ConcurrentBag
ms.date: 05/01/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- object pool, in .NET Framework
ms.assetid: 0480e7ff-b6f9-480e-a889-2ed4264d8372
ms.openlocfilehash: 64d91162b27eba80fba63761d0a926e441b63440
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287861"
---
# <a name="create-an-object-pool-by-using-a-concurrentbag"></a><span data-ttu-id="c905b-102">Creare un pool di oggetti usando un ConcurrentBag</span><span class="sxs-lookup"><span data-stu-id="c905b-102">Create an object pool by using a ConcurrentBag</span></span>

<span data-ttu-id="c905b-103">Questo esempio illustra come usare un <xref:System.Collections.Concurrent.ConcurrentBag%601> oggetto per implementare un pool di oggetti.</span><span class="sxs-lookup"><span data-stu-id="c905b-103">This example shows how to use a <xref:System.Collections.Concurrent.ConcurrentBag%601> to implement an object pool.</span></span> <span data-ttu-id="c905b-104">I pool di oggetti possono migliorare le prestazioni dell'applicazione in situazioni in cui vengono richieste più istanze di una classe e la classe è costosa da creare o eliminare.</span><span class="sxs-lookup"><span data-stu-id="c905b-104">Object pools can improve application performance in situations where you require multiple instances of a class and the class is expensive to create or destroy.</span></span> <span data-ttu-id="c905b-105">Quando un programma client richiede un nuovo oggetto, il pool di oggetti prima tenta di specificarne uno che è già stato creato e restituito al pool.</span><span class="sxs-lookup"><span data-stu-id="c905b-105">When a client program requests a new object, the object pool first attempts to provide one that has already been created and returned to the pool.</span></span> <span data-ttu-id="c905b-106">Se non è disponibile nessun oggetto, solo in questo caso viene creato.</span><span class="sxs-lookup"><span data-stu-id="c905b-106">If none is available, only then is a new object created.</span></span>

<span data-ttu-id="c905b-107">L'oggetto <xref:System.Collections.Concurrent.ConcurrentBag%601> viene utilizzato per archiviare gli oggetti poiché supporta inserimento e rimozione veloci, specialmente quando lo stesso thread aggiunge e rimuove elementi.</span><span class="sxs-lookup"><span data-stu-id="c905b-107">The <xref:System.Collections.Concurrent.ConcurrentBag%601> is used to store the objects because it supports fast insertion and removal, especially when the same thread is both adding and removing items.</span></span> <span data-ttu-id="c905b-108">Questo esempio potrebbe essere ulteriormente ampliato in modo da essere compilato in base a un oggetto <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, implementato dalla struttura dei dati del contenitore, così come <xref:System.Collections.Concurrent.ConcurrentQueue%601> e <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span><span class="sxs-lookup"><span data-stu-id="c905b-108">This example could be further augmented to be built around a <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, which the bag data structure implements, as do <xref:System.Collections.Concurrent.ConcurrentQueue%601> and <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span></span>

> [!TIP]
> <span data-ttu-id="c905b-109">Questo articolo descrive come scrivere un'implementazione personalizzata di un pool di oggetti con un tipo simultaneo sottostante per archiviare gli oggetti da riutilizzare.</span><span class="sxs-lookup"><span data-stu-id="c905b-109">This article defines how to write your own implementation of an object pool with an underlying concurrent type to store objects for reuse.</span></span> <span data-ttu-id="c905b-110">Tuttavia, il <xref:Microsoft.Extensions.ObjectPool.ObjectPool%601?displayProperty=nameWithType> tipo esiste già nello <xref:Microsoft.Extensions.ObjectPool?displayProperty=fullName> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c905b-110">However, the <xref:Microsoft.Extensions.ObjectPool.ObjectPool%601?displayProperty=nameWithType> type already exists under the <xref:Microsoft.Extensions.ObjectPool?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="c905b-111">Provare a usare il tipo disponibile prima di creare un'implementazione personalizzata, che include molte funzionalità aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="c905b-111">Consider using the available type before creating your own implementation, which includes many additional features.</span></span>

## <a name="example"></a><span data-ttu-id="c905b-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="c905b-112">Example</span></span>

[!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
[!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]

## <a name="see-also"></a><span data-ttu-id="c905b-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c905b-113">See also</span></span>

- [<span data-ttu-id="c905b-114">Raccolte thread-safe</span><span class="sxs-lookup"><span data-stu-id="c905b-114">Thread-Safe Collections</span></span>](index.md)
