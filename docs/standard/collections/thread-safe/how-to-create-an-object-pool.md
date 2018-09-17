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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0bc0c6bebbab6e84c165f41300a4cb16c8746a07
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2018
ms.locfileid: "45597299"
---
# <a name="how-to-create-an-object-pool-by-using-a-concurrentbag"></a>Procedura: Creare un pool di oggetti con un oggetto ConcurrentBag
Questo esempio illustra come usare un contenitore simultaneo per implementare un pool di oggetti. I pool di oggetti possono migliorare le prestazioni dell'applicazione in situazioni in cui vengono richieste più istanze di una classe e la classe è costosa da creare o eliminare. Quando un programma client richiede un nuovo oggetto, il pool di oggetti prima tenta di specificarne uno che è già stato creato e restituito al pool. Se non è disponibile nessun oggetto, solo in questo caso viene creato.  
  
 <xref:System.Collections.Concurrent.ConcurrentBag%601> viene usato per archiviare gli oggetti poiché supporta inserimento e rimozione veloci, specialmente quando lo stesso thread aggiunge e rimuove gli elementi. Questo esempio potrebbe essere ulteriormente ampliato in modo da essere compilato in base a un oggetto <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, implementato dalla struttura dei dati del contenitore, così come <xref:System.Collections.Concurrent.ConcurrentQueue%601> e <xref:System.Collections.Concurrent.ConcurrentStack%601>.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
 [!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]  
  
## <a name="see-also"></a>Vedere anche

- [Raccolte thread-safe](../../../../docs/standard/collections/thread-safe/index.md)
