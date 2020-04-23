---
title: Raccolta comunità compensata tra workstation e server
description: Informazioni su operazioni di Garbage Collection per workstation e server in .NET.
ms.date: 04/21/2020
helpviewer_keywords:
- garbage collection, workstation
- garbage collection, server
- workstation garbage collection
- server garbage collection
ms.openlocfilehash: 6b8e5f6802e5d44669b95d43d4e897fa4a418512
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82103555"
---
# <a name="workstation-and-server-garbage-collection"></a>Operazione di Garbage Collection per workstation e server

Il Garbage Collector si regola da sé e può funzionare in un'ampia varietà di scenari. Tuttavia, è possibile [impostare il tipo di Garbage Collection](../../core/run-time-config/garbage-collector.md#flavors-of-garbage-collection) in base alle caratteristiche del carico di lavoro. CLR fornisce i seguenti tipi di Garbage Collection:

- Garbage Collection per workstation (GC), progettato per le app client. È la versione GC predefinita per le app autonome. Per le app ospitate, ad esempio quelle ospitate da ASP.NET, l'host determina la versione GC predefinita.

  Le operazioni di Garbage Collection per workstation possono essere eseguite in modalità simultanea o non simultanea. La procedura di Garbage Collection simultanea (o *in background)* consente ai thread gestiti di continuare le operazioni durante un'operazione di Garbage Collection. [L'operazione di Garbage Collection](background-gc.md) in background sostituisce la [garbage collection simultanea](background-gc.md#concurrent-garbage-collection) in .NET Framework 4 e versioni successive.

- Garbage Collection per server, per le applicazioni server che richiedono scalabilità e velocità effettiva elevata.

  - In .NET Core la procedura di Garbage Collection per server può essere non simultanea o in background.

  - In .NET Framework 4.5 e versioni successive, la procedura di Garbage Collection per server può essere non simultanea o in background. In .NET Framework 4 e versioni precedenti, la procedura di Garbage Collection per server non è simultanea.

Nella figura seguente vengono illustrati i thread dedicati che eseguono l'operazione di Garbage Collection in un server:The following illustration shows the dedicated threads that perform the garbage collection on a server:

![Thread di Garbage Collection server](./media/gc-server.png)

## <a name="performance-considerations"></a>Considerazioni sulle prestazioni

### <a name="workstation-gc"></a>GC workstation

Di seguito sono riportate alcune considerazioni su threading e prestazioni per l'operazione di Garbage Collection per workstation:

- La raccolta viene eseguita nel thread dell'utente che ha attivato l'operazione di Garbage Collection e mantiene la stessa priorità. Poiché i thread dell'utente vengono in genere eseguiti con priorità normale, il Garbage Collector (eseguito in un thread con priorità normale) deve competere con altri thread per il tempo CPU. I thread che eseguono codice nativo non vengono sospesi in caso di Garbage Collection per server o workstation.

- La procedura di Garbage Collection per workstation viene sempre utilizzata in un computer che dispone di un solo processore, indipendentemente [dall'impostazione](../../core/run-time-config/garbage-collector.md#systemgcservercomplus_gcserver)di configurazione.

### <a name="server-gc"></a>GC server

Di seguito sono riportate alcune considerazioni su threading e prestazioni per l'operazione di Garbage Collection per server:

- La raccolta viene eseguita in più thread dedicati eseguiti con livello di priorità `THREAD_PRIORITY_HIGHEST` .

- Per ogni CPU vengono forniti un heap e un thread dedicato per l'esecuzione dell'operazione di Garbage Collection. Gli heap vengono raccolti contemporaneamente. Ogni heap contiene un heap degli oggetti piccoli e un heap degli oggetti grandi; è possibile accedere a tutti gli heap tramite codice utente. Gli oggetti contenuti in heap diversi possono fare riferimento l'un l'altro.

- Grazie all'utilizzo congiunto di più thread di Garbage Collection, le operazioni di Garbage Collection per server saranno più veloci delle operazioni per workstation in un heap di pari dimensioni.

- I segmenti di Garbage Collection per server sono spesso di dimensioni maggiori. Tuttavia, questa è solo una generalizzazione: la dimensione del segmento è specifica dell'implementazione ed è soggetta a modifiche. Non fare supposizioni sulle dimensioni dei segmenti allocati dal Garbage Collector durante l'ottimizzazione dell'app.

- Le operazioni di Garbage Collection per server possono richiedere un utilizzo di risorse elevato. Si supponga, ad esempio, che siano presenti 12 processi che utilizzano il catalogo globale del server in esecuzione in un computer con quattro processori. Se tutti i processi si verificano per raccogliere spazzatura allo stesso tempo, avrebbero interferire con l'altro, come ci sarebbero 12 thread pianificati sullo stesso processore. Se i processi sono attivi, non è una buona idea che tutti utilizzino il catalogo globale del server.

Se si eseguono centinaia di istanze di un'applicazione, prendere in considerazione l'utilizzo di Garbage Collection per workstation con l'operazione di Garbage Collection simultanea disabilitata. Si avranno meno cambi di contesto e un possibile miglioramento delle prestazioni.

## <a name="see-also"></a>Vedere anche

- [Garbage Collection in background](background-gc.md)
- [Opzioni di configurazione in fase di esecuzione per la procedura di Garbage CollectionRun-time configuration options for garbage collection](../../core/run-time-config/garbage-collector.md)
