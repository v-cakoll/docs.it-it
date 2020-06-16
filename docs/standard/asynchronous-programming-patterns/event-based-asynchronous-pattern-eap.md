---
title: Modello asincrono basato su eventi (EAP)
description: Vedere collegamenti ad articoli relativi al modello asincrono basato su eventi (EAP) in .NET, ad esempio implementazione, procedure consigliate, implementazione di un client EAP e altro ancora.
ms.date: 07/23/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous calls
- asynchronous programming, design patterns
- asynchronous programming
ms.assetid: c6baed9f-2a25-4728-9a9a-53b7b14840cf
ms.openlocfilehash: 03b4d914d72b96b882c774565654c022b145b5f2
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768872"
---
# <a name="event-based-asynchronous-pattern-eap"></a>Modello asincrono basato su eventi (EAP)

È possibile esporre funzionalità asincrone al codice client in molti modi. Il modello asincrono basato su eventi determina l'unico modo per la presentazione del comportamento asincrono da parte delle classi.  
  
> [!NOTE]
> A partire da .NET Framework 4, Task Parallel Library fornisce un nuovo modello di programmazione asincrona e parallela. Per altre informazioni, vedere [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md) e [Task-based Asynchronous Pattern (TAP)](task-based-asynchronous-pattern-tap.md).
  
## <a name="in-this-section"></a>Contenuto della sezione

 [Cenni preliminari sul modello asincrono basato su eventi](event-based-asynchronous-pattern-overview.md)  
 Descrive il modo in cui il modello asincrono basato su eventi rende disponibili i vantaggi delle applicazioni multithread, nascondendo al tempo stesso molti dei problemi complessi correlati alla progettazione multithread.  
  
 [Implementazione del modello asincrono basato su eventi](implementing-the-event-based-asynchronous-pattern.md)  
 Descrive il modo standardizzato di creare un pacchetto di una classe con funzionalità asincrone.  
  
 [Suggerimenti per l'implementazione del modello asincrono basato su eventi](best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 Descrive i requisiti per l'esposizione di funzionalità asincrone in base al modello asincrono basato su eventi.  
  
 [Quando implementare il modello asincrono basato su eventi](deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 Descrive come stabilire quando occorre scegliere di implementare il modello asincrono basato su eventi anziché il modello <xref:System.IAsyncResult> rappresentato dal [modello di programmazione asincrona (APM)](asynchronous-programming-model-apm.md)
  
 [Procedura: implementare un componente che supporta il modello asincrono basato su eventi](component-that-supports-the-event-based-asynchronous-pattern.md)  
 Spiega come creare un componente che implementa un modello asincrono basato su eventi. L'implementazione è eseguita mediante classi di helper dallo spazio dei nomi <xref:System.ComponentModel?displayProperty=nameWithType>, in modo da assicurare che il componente funzioni correttamente con qualsiasi modello di applicazione.  

 [Procedura: implementare un client del modello asincrono basato su eventi](how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md)  
 Spiega come creare un client che usa un componente che implementa un modello asincrono basato su eventi.
  
 [Procedura: usare componenti che supportano il modello asincrono basato su eventi](how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 Descrive come usare un componente che supporta il modello asincrono basato su eventi.  
  
## <a name="reference"></a>Informazioni di riferimento

 <xref:System.ComponentModel.AsyncOperation>  
 Descrive la classe <xref:System.ComponentModel.AsyncOperation> e include collegamenti a tutti i membri corrispondenti.  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 Descrive la classe <xref:System.ComponentModel.AsyncOperationManager> e include collegamenti a tutti i membri corrispondenti.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Descrive il componente <xref:System.ComponentModel.BackgroundWorker> e include collegamenti a tutti i membri corrispondenti.  
  
## <a name="related-sections"></a>Sezioni correlate

 [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md)  
 Descrive un modello di programmazione delle operazioni asincrone e parallele.  
  
 [Threading](../threading/index.md)  
 Descrive le funzionalità di multithreading in .NET.  
  
## <a name="see-also"></a>Vedere anche

- [Procedure consigliate per il threading gestito](../threading/managed-threading-best-practices.md)
- [Events](../events/index.md)
- [Modelli di programmazione asincrona](index.md)
