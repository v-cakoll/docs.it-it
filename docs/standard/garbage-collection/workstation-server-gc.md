---
title: Workstation e server Garbage Collection (GC)
description: Informazioni sulle Garbage Collection di workstation e server in .NET.
ms.date: 04/21/2020
helpviewer_keywords:
- garbage collection, workstation
- garbage collection, server
- workstation garbage collection
- server garbage collection
ms.openlocfilehash: 5ff2b1fe2f997913e071f35ec5abb167ed757608
ms.sourcegitcommit: 5280b2aef60a1ed99002dba44e4b9e7f6c830604
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84306695"
---
# <a name="workstation-and-server-garbage-collection"></a>Operazione di Garbage Collection per workstation e server

Il Garbage Collector si regola da sé e può funzionare in un'ampia varietà di scenari. Tuttavia, è possibile [impostare il tipo di Garbage Collection](../../core/run-time-config/garbage-collector.md#flavors-of-garbage-collection) in base alle caratteristiche del carico di lavoro. CLR fornisce i seguenti tipi di Garbage Collection:

- Workstation Garbage Collection (GC), progettato per le app client. Si tratta della versione GC predefinita per le app autonome. Per le app ospitate, ad esempio quelle ospitate da ASP.NET, l'host determina la versione predefinita del catalogo globale.

  Le operazioni di Garbage Collection per workstation possono essere eseguite in modalità simultanea o non simultanea. Il Garbage Collection simultaneo (o *sfondo*) consente ai thread gestiti di continuare le operazioni durante una Garbage Collection. [Garbage Collection in background](background-gc.md) sostituisce [Garbage Collection simultanee](background-gc.md#concurrent-garbage-collection) in .NET Framework 4 e versioni successive.

- Garbage Collection per server, per le applicazioni server che richiedono scalabilità e velocità effettiva elevata.

  - In .NET Core, il Garbage Collection server può essere non simultaneo o in background.

  - In .NET Framework 4,5 e versioni successive, il server Garbage Collection può essere non simultaneo o in background. In .NET Framework 4 e versioni precedenti, Garbage Collection server non è simultaneo.

Nella figura seguente vengono illustrati i thread dedicati che eseguono il Garbage Collection in un server:

![Thread di Garbage Collection server](media/gc-server.png)

## <a name="performance-considerations"></a>Considerazioni sulle prestazioni

### <a name="workstation-gc"></a>GC workstation

Di seguito sono riportate alcune considerazioni su threading e prestazioni per l'operazione di Garbage Collection per workstation:

- La raccolta viene eseguita nel thread dell'utente che ha attivato l'operazione di Garbage Collection e mantiene la stessa priorità. Poiché i thread dell'utente vengono in genere eseguiti con priorità normale, il Garbage Collector (eseguito in un thread con priorità normale) deve competere con altri thread per il tempo CPU. I thread che eseguono codice nativo non vengono sospesi sul server o sulla workstation Garbage Collection.

- La workstation Garbage Collection viene sempre utilizzata in un computer con un solo processore, indipendentemente dall' [impostazione di configurazione](../../core/run-time-config/garbage-collector.md#systemgcservercomplus_gcserver).

### <a name="server-gc"></a>GC server

Di seguito sono riportate alcune considerazioni su threading e prestazioni per l'operazione di Garbage Collection per server:

- La raccolta viene eseguita in più thread dedicati eseguiti con livello di priorità `THREAD_PRIORITY_HIGHEST` .

- Per ogni CPU vengono forniti un heap e un thread dedicato per l'esecuzione dell'operazione di Garbage Collection. Gli heap vengono raccolti contemporaneamente. Ogni heap contiene un heap degli oggetti piccoli e un heap degli oggetti grandi; è possibile accedere a tutti gli heap tramite codice utente. Gli oggetti contenuti in heap diversi possono fare riferimento l'un l'altro.

- Grazie all'utilizzo congiunto di più thread di Garbage Collection, le operazioni di Garbage Collection per server saranno più veloci delle operazioni per workstation in un heap di pari dimensioni.

- I segmenti di Garbage Collection per server sono spesso di dimensioni maggiori. Tuttavia, questa è solo una generalizzazione: le dimensioni del segmento sono specifiche dell'implementazione ed è soggetta a modifiche. Non fare supposizioni sulle dimensioni dei segmenti allocati dal Garbage Collector durante l'ottimizzazione dell'app.

- Le operazioni di Garbage Collection per server possono richiedere un utilizzo di risorse elevato. Si supponga, ad esempio, che siano presenti 12 processi che utilizzano il GC server in esecuzione in un computer che dispone di quattro processori. Se tutti i processi si verificano per la raccolta di Garbage Collection allo stesso tempo, interferiscono tra loro, perché sono presenti 12 thread pianificati nello stesso processore. Se i processi sono attivi, non è consigliabile che tutti usino il GC del server.

Se si eseguono centinaia di istanze di un'applicazione, è consigliabile usare Garbage Collection workstation con Garbage Collection simultanee disabilitate. Si avranno meno cambi di contesto e un possibile miglioramento delle prestazioni.

## <a name="see-also"></a>Vedere anche

- [Garbage Collection in background](background-gc.md)
- [Opzioni di configurazione in fase di esecuzione per Garbage Collection](../../core/run-time-config/garbage-collector.md)
