---
title: 'Procedura: Creare un pool di oggetti con un oggetto ConcurrentBag'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- object pool, in .NET Framework
ms.assetid: 0480e7ff-b6f9-480e-a889-2ed4264d8372
ms.openlocfilehash: 888521eb5c3c3169c4b39a26e82fef2e35c286d9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711272"
---
# <a name="how-to-create-an-object-pool-by-using-a-concurrentbag"></a><span data-ttu-id="45f35-102">Procedura: Creare un pool di oggetti con un oggetto ConcurrentBag</span><span class="sxs-lookup"><span data-stu-id="45f35-102">How to: Create an Object Pool by Using a ConcurrentBag</span></span>
<span data-ttu-id="45f35-103">Questo esempio illustra come usare un contenitore simultaneo per implementare un pool di oggetti.</span><span class="sxs-lookup"><span data-stu-id="45f35-103">This example shows how to use a concurrent bag to implement an object pool.</span></span> <span data-ttu-id="45f35-104">I pool di oggetti possono migliorare le prestazioni dell'applicazione in situazioni in cui vengono richieste più istanze di una classe e la classe è costosa da creare o eliminare.</span><span class="sxs-lookup"><span data-stu-id="45f35-104">Object pools can improve application performance in situations where you require multiple instances of a class and the class is expensive to create or destroy.</span></span> <span data-ttu-id="45f35-105">Quando un programma client richiede un nuovo oggetto, il pool di oggetti prima tenta di specificarne uno che è già stato creato e restituito al pool.</span><span class="sxs-lookup"><span data-stu-id="45f35-105">When a client program requests a new object, the object pool first attempts to provide one that has already been created and returned to the pool.</span></span> <span data-ttu-id="45f35-106">Se non è disponibile nessun oggetto, solo in questo caso viene creato.</span><span class="sxs-lookup"><span data-stu-id="45f35-106">If none is available, only then is a new object created.</span></span>  
  
 <span data-ttu-id="45f35-107"><xref:System.Collections.Concurrent.ConcurrentBag%601> viene usato per archiviare gli oggetti poiché supporta inserimento e rimozione veloci, specialmente quando lo stesso thread aggiunge e rimuove gli elementi.</span><span class="sxs-lookup"><span data-stu-id="45f35-107"><xref:System.Collections.Concurrent.ConcurrentBag%601> is used to store the objects because it supports fast insertion and removal, especially when the same thread is both adding and removing items.</span></span> <span data-ttu-id="45f35-108">Questo esempio potrebbe essere ulteriormente ampliato in modo da essere compilato in base a un oggetto <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, implementato dalla struttura dei dati del contenitore, così come <xref:System.Collections.Concurrent.ConcurrentQueue%601> e <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span><span class="sxs-lookup"><span data-stu-id="45f35-108">This example could be further augmented to be built around a <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, which the bag data structure implements, as do <xref:System.Collections.Concurrent.ConcurrentQueue%601> and <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45f35-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="45f35-109">Example</span></span>  
 [!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
 [!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]  
  
## <a name="see-also"></a><span data-ttu-id="45f35-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45f35-110">See also</span></span>

- [<span data-ttu-id="45f35-111">Raccolte thread-safe</span><span class="sxs-lookup"><span data-stu-id="45f35-111">Thread-Safe Collections</span></span>](../../../../docs/standard/collections/thread-safe/index.md)
