---
title: Modello asincrono basato su eventi (EAP)
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous calls
- asynchronous programming, design patterns
- asynchronous programming
ms.assetid: c6baed9f-2a25-4728-9a9a-53b7b14840cf
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7811113244d8c5f7d79a55ebb01f04e99e9bd2a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33567806"
---
# <a name="event-based-asynchronous-pattern-eap"></a>Modello asincrono basato su eventi (EAP)
È possibile esporre funzionalità asincrone al codice client in molti modi. Il modello asincrono basato su eventi determina l'unico modo per la presentazione del comportamento asincrono da parte delle classi.  
  
> [!NOTE]
>  A partire da [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Task Parallel Library fornisce un nuovo modello di programmazione asincrona e parallela. Per altre informazioni, vedere [Programmazione parallela](../../../docs/standard/parallel-programming/index.md).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Panoramica sul modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 Descrive il modo in cui il modello asincrono basato su eventi rende disponibili i vantaggi delle applicazioni multithread, nascondendo al tempo stesso molti dei problemi complessi correlati alla progettazione multithread.  
  
 [Implementazione del modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 Descrive il modo standardizzato di creare un pacchetto di una classe con funzionalità asincrone.  
  
 [Suggerimenti per l'implementazione del modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 Descrive i requisiti per l'esposizione di funzionalità asincrone in base al modello asincrono basato su eventi.  
  
 [Quando implementare il modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 Descrive come determinare quando occorre scegliere di implementare il modello asincrono basato su eventi invece del modello <xref:System.IAsyncResult>.  
  
 [Procedura dettagliata: implementazione di un componente che supporta il modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 Illustra come creare un componente che implementa un modello asincrono basato su eventi. L'implementazione è eseguita mediante classi di helper dallo spazio dei nomi <xref:System.ComponentModel?displayProperty=nameWithType>, in modo da assicurare che il componente funzioni correttamente con qualsiasi modello di applicazione.  
  
 [Procedura: Usare componenti che supportano il modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 Descrive come usare un componente che supporta il modello asincrono basato su eventi.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.ComponentModel.AsyncOperation>  
 Descrive la classe <xref:System.ComponentModel.AsyncOperation> e include collegamenti a tutti i membri corrispondenti.  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 Descrive la classe <xref:System.ComponentModel.AsyncOperationManager> e include collegamenti a tutti i membri corrispondenti.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Descrive il componente <xref:System.ComponentModel.BackgroundWorker> e include collegamenti a tutti i membri corrispondenti.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Task Parallel Library (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 Descrive un modello di programmazione delle operazioni asincrone e parallele.  
  
 [Threading](../../../docs/standard/threading/index.md)  
 Descrive le funzionalità di multithreading nel.NET Framework.  
  
 [Threading](https://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c)  
 Descrive le funzionalità di multithreading nei linguaggi C# e Visual Basic.  
  
## <a name="see-also"></a>Vedere anche  
 [Suggerimenti per l'utilizzo del threading gestito](../../../docs/standard/threading/managed-threading-best-practices.md)  
 [Eventi](../../../docs/standard/events/index.md)  
 [Multithreading nei componenti](https://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)  
 [Modelli di programmazione asincrona](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
