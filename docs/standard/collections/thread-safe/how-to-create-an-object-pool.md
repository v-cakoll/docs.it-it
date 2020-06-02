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
# <a name="create-an-object-pool-by-using-a-concurrentbag"></a>Creare un pool di oggetti usando un ConcurrentBag

Questo esempio illustra come usare un <xref:System.Collections.Concurrent.ConcurrentBag%601> oggetto per implementare un pool di oggetti. I pool di oggetti possono migliorare le prestazioni dell'applicazione in situazioni in cui vengono richieste più istanze di una classe e la classe è costosa da creare o eliminare. Quando un programma client richiede un nuovo oggetto, il pool di oggetti prima tenta di specificarne uno che è già stato creato e restituito al pool. Se non è disponibile nessun oggetto, solo in questo caso viene creato.

L'oggetto <xref:System.Collections.Concurrent.ConcurrentBag%601> viene utilizzato per archiviare gli oggetti poiché supporta inserimento e rimozione veloci, specialmente quando lo stesso thread aggiunge e rimuove elementi. Questo esempio potrebbe essere ulteriormente ampliato in modo da essere compilato in base a un oggetto <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, implementato dalla struttura dei dati del contenitore, così come <xref:System.Collections.Concurrent.ConcurrentQueue%601> e <xref:System.Collections.Concurrent.ConcurrentStack%601>.

> [!TIP]
> Questo articolo descrive come scrivere un'implementazione personalizzata di un pool di oggetti con un tipo simultaneo sottostante per archiviare gli oggetti da riutilizzare. Tuttavia, il <xref:Microsoft.Extensions.ObjectPool.ObjectPool%601?displayProperty=nameWithType> tipo esiste già nello <xref:Microsoft.Extensions.ObjectPool?displayProperty=fullName> spazio dei nomi. Provare a usare il tipo disponibile prima di creare un'implementazione personalizzata, che include molte funzionalità aggiuntive.

## <a name="example"></a>Esempio

[!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
[!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]

## <a name="see-also"></a>Vedere anche

- [Raccolte thread-safe](index.md)
