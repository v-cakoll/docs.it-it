---
title: Modalità di latenza
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- garbage collection, intrusiveness
- garbage collection, latency modes
ms.assetid: 96278bb7-6eab-4612-8594-ceebfc887d81
ms.openlocfilehash: ee45fe5e8016c7507bc3a873e615fd8379810a8e
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286015"
---
# <a name="latency-modes"></a>Modalità di latenza

Per recuperare oggetti, è necessario che il Garbage Collector (GC) interrompa tutti i thread in esecuzione in un'applicazione. Il periodo di tempo durante il quale il Garbage Collector è attivo viene definito *latenza*.

In alcune situazioni, ad esempio quando un'applicazione recupera dati o visualizza contenuto, un'operazione completa di Garbage Collection può verificarsi in un momento critico e può ostacolare le prestazioni. È possibile rettificare l'ingerenza del Garbage Collector impostando la proprietà <xref:System.Runtime.GCSettings.LatencyMode%2A?displayProperty=nameWithType> su uno dei valori <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType>.

## <a name="low-latency-settings"></a>Impostazioni a bassa latenza

Se si usa un'impostazione di latenza "bassa", l'Garbage Collector inserirà un minor numero di risorse nell'applicazione. L'operazione di Garbage Collection è più conservativa sul recupero della memoria.

Tramite l'enumerazione <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType> vengono fornite due impostazioni a bassa latenza:

- [GCLatencyMode. LowLatency](xref:System.Runtime.GCLatencyMode.LowLatency) disattiva le raccolte di generazione 2 ed esegue solo le raccolte di generazione 0 e 1. Può essere usato solo per brevi periodi di tempo. In caso di lunghi periodi, se viene usata una quantità elevata di memoria, tramite il Garbage Collector verrà attivata una raccolta mediante la quale è possibile mettere in pausa brevemente l'applicazione e interrompere un'operazione critica rispetto al tempo. Questa impostazione è disponibile solo per le operazioni di Garbage Collection per workstation.

- [GCLatencyMode. SustainedLowLatency](xref:System.Runtime.GCLatencyMode.SustainedLowLatency) evita le raccolte di primo piano di generazione 2 ed esegue solo le raccolte di generazione 0, 1 e di seconda generazione in background. Può essere usato per periodi di tempo più lunghi ed è disponibile per le operazioni di Garbage Collection per workstation e per server. Questa impostazione non può essere utilizzata se Garbage Collection in background è disabilitata.

Durante i periodi di bassa latenza, le raccolte di generazione 2 vengono soppresse eccetto nei seguenti casi:

- Il sistema riceve una notifica di memoria insufficiente dal sistema operativo.

- Il codice dell'applicazione induce una raccolta chiamando il <xref:System.GC.Collect%2A?displayProperty=nameWithType> metodo e specificando 2 per il `generation` parametro.

## <a name="scenarios"></a>Scenari

La tabella seguente elenca gli scenari di applicazione per l'uso dei <xref:System.Runtime.GCLatencyMode> valori:

|Modalità di latenza|Scenari applicativi|
|------------------|---------------------------|
|<xref:System.Runtime.GCLatencyMode.Batch>|Per le applicazioni che non hanno alcuna interfaccia utente o operazioni lato server.<br /><br />Quando Garbage Collection in background è disabilitato, questa è la modalità predefinita per workstation e server Garbage Collection. <xref:System.Runtime.GCLatencyMode.Batch>anche la modalità esegue l'override dell'impostazione [gcConcurrent](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) , ovvero impedisce raccolte in background o simultanee.|
|<xref:System.Runtime.GCLatencyMode.Interactive>|Per la maggior parte delle applicazioni che hanno una interfaccia utente.<br /><br />Questa è la modalità predefinita per workstation e server Garbage Collection. Tuttavia, se un'app è ospitata, le impostazioni Garbage Collector del processo di hosting hanno la precedenza.|
|<xref:System.Runtime.GCLatencyMode.LowLatency>|Per le applicazioni con operazioni a breve termine, per cui il tempo riveste un'importanza significativa, durante le quali le interruzioni del Garbage Collector potrebbero rivelarsi dannose. Ad esempio, le applicazioni che eseguono il rendering delle animazioni o delle funzioni di acquisizione dei dati.|
|<xref:System.Runtime.GCLatencyMode.SustainedLowLatency>|Per le applicazioni con operazioni per cui i tempi sono importanti per una durata contenuta, ma potenzialmente lunga, durante la quale le interruzioni del Garbage Collector potrebbero rivelarsi dannose. Ad esempio, le applicazioni per cui sono richiesti tempi di risposta rapidi come i cambiamenti dei dati di mercato durante le ore di negoziazione.<br /><br />Questa modalità comporta dimensioni dell'heap gestito maggiori rispetto ad altre. Poiché non consente di comprimere l'heap gestito, è possibile avere una maggiore frammentazione. Assicurarsi che sia disponibile memoria sufficiente.|

## <a name="guidelines-for-using-low-latency"></a>Linee guida per l'utilizzo della bassa latenza

Quando si usa la modalità [GCLatencyMode. LowLatency](xref:System.Runtime.GCLatencyMode.LowLatency) , tenere presenti le linee guida seguenti:

- Mantenere il periodo di tempo in bassa latenza più brevemente possibile.

- Evitare di allocare quantità di memoria elevate durante i periodi di bassa latenza. Possono verificarsi notifiche di memoria insufficiente perché le operazioni di Garbage Collection recuperano meno oggetti.

- In modalità a bassa latenza, ridurre al minimo il numero di nuove allocazioni, in particolare le allocazioni sull'heap degli oggetti grandi e sugli oggetti bloccati.

- Tenere presenti i thread che potrebbero essere in corso di allocazione. Poiché l' <xref:System.Runtime.GCSettings.LatencyMode%2A> impostazione della proprietà è a livello di processo, le <xref:System.OutOfMemoryException> eccezioni possono essere generate in qualsiasi thread che sta allocando.

- Eseguire il wrapping del codice a bassa latenza nelle aree a esecuzione vincolata. Per altre informazioni, vedere [aree di esecuzione vincolate](../../framework/performance/constrained-execution-regions.md).

- È possibile forzare le operazioni di Garbage Collection di generazione 2 durante un periodo di bassa latenza chiamando il metodo <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%29?displayProperty=nameWithType>.

## <a name="see-also"></a>Vedere anche

- <xref:System.GC?displayProperty=nameWithType>
- [Raccolte indotte](induced.md)
- [Garbage Collection](index.md)
