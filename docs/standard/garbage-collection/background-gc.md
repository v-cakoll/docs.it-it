---
title: Garbage Collection in background
description: Informazioni sulle Garbage Collection in background in .NET e su come si differenziano in workstation e Garbage Collection server.
ms.date: 04/21/2020
helpviewer_keywords:
- garbage collection, background
- background garbage collection
ms.openlocfilehash: 8134c0af55d74e57dcfce8c7174265b8c9902feb
ms.sourcegitcommit: 5280b2aef60a1ed99002dba44e4b9e7f6c830604
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84307072"
---
# <a name="background-garbage-collection"></a>Garbage Collection in background

In background Garbage Collection (GC) le generazioni temporanee (0 e 1) vengono raccolte in base alle esigenze mentre è in corso la raccolta di generazione 2. Il Garbage Collection in background viene eseguito su uno o più thread dedicati, a seconda che si tratti di un GC di base o del server e si applica solo alle raccolte di generazione 2.

Il Garbage Collection in background è abilitato per impostazione predefinita. Può essere abilitata o disabilitata con l'impostazione di configurazione [gcConcurrent](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) nell'impostazione .NET Framework app o [System. GC. Concurrent](../../core/run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent) nelle app .NET Core.

> [!NOTE]
> In background Garbage Collection sostituisce [Garbage Collection simultanei](#concurrent-garbage-collection) ed è disponibile in .NET Framework 4 e versioni successive. In .NET Framework 4 è supportato solo per Garbage Collection *workstation* . A partire da .NET Framework 4,5, Garbage Collection in background è disponibile sia per la *workstation* che per il Garbage Collection *Server* .

Una raccolta nelle generazioni temporanee durante Garbage Collection in background è nota come Garbage Collection in *primo piano* . Durante l'esecuzione di un'operazione di Garbage Collection in primo piano, tutti i thread gestiti vengono sospesi.

Quando lo sfondo Garbage Collection è in corso ed è stato allocato un numero sufficiente di oggetti nella generazione 0, CLR esegue una Garbage Collection di primo piano di generazione 0 o 1. Il thread di Garbage Collection in background dedicato esegue controlli in corrispondenza di punti sicuri frequenti per stabilire se vi sia una richiesta di Garbage Collection in primo piano. In caso affermativo, la raccolta in background si autosospende in modo che possa essere eseguita l'operazione in primo piano. Una volta completato il Garbage Collection in primo piano, lo sfondo dedicato Garbage Collection thread e thread utente riprende.

La modalità in background elimina le restrizioni di allocazione imposte dalla modalità simultanea, dal momento che durante un'operazione di Garbage Collection in background è possibile eseguire operazioni temporanee. In background Garbage Collection possibile rimuovere gli oggetti inattivi in generazioni effimere. Può anche espandere l'heap, se necessario, durante un Garbage Collection di generazione 1.

## <a name="background-workstation-vs-server-gc"></a>GC della workstation in background rispetto al server

A partire da .NET Framework 4,5, Garbage Collection in background è disponibile per il catalogo globale del server. GC in background è la modalità predefinita per il server Garbage Collection.

Il server in background Garbage Collection funziona in modo analogo alla Garbage Collection workstation in background, ma esistono alcune differenze:

- Garbage Collection workstation in background usa uno sfondo dedicato Garbage Collection thread, mentre il server in background Garbage Collection usa più thread. In genere è presente un thread dedicato per ogni processore logico.

- A differenza dello sfondo della workstation Garbage Collection thread, il timeout dei thread GC del server in background non viene eseguito.

Nell'illustrazione seguente viene mostrata Garbage Collection *workstation* in background eseguita su un thread separato dedicato:

![Garbage Collection della workstation in background](media/fundamentals/background-workstation-garbage-collection.png)

Nella figura seguente viene illustrato il *Server* in background Garbage Collection eseguito su thread separati dedicati:

![Garbage Collection del server in background](media/fundamentals/background-server-garbage-collection.png)

## <a name="concurrent-garbage-collection"></a>Garbage Collection contemporanea

> [!TIP]
> Questa sezione si applica a:
>
> - .NET Framework 3,5 e versioni precedenti per la workstation Garbage Collection
> - .NET Framework 4 e versioni precedenti per Garbage Collection server
>
> Il Garbage Collector simultaneo viene sostituito da Garbage Collection in background nelle versioni successive.

In workstation o server Garbage Collection è possibile [abilitare la Garbage Collection simultanea](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md), che consente di eseguire i thread contemporaneamente a un thread dedicato che esegue l'Garbage Collection per la maggior parte della durata della raccolta. Questa opzione ha effetto solo sulle operazioni di Garbage Collection nella generazione 2. le generazioni 0 e 1 sono sempre non simultanee perché terminano rapidamente.

La modalità simultanea consente alle applicazioni interattive una maggiore efficienza di risposta riducendo al minimo le pause di una raccolta. È possibile continuare a eseguire i thread gestiti per la maggior parte del tempo in cui viene eseguito il thread di Garbage Collection in modalità simultanea. Il risultato saranno pause più brevi durante l'esecuzione di un'operazione di Garbage Collection.

La modalità simultanea di Garbage Collection viene eseguita in un thread dedicato. Per impostazione predefinita, CLR esegue Garbage Collection di workstation con Garbage Collection simultanea abilitata nei computer a processore singolo e a più processori.

Nell'illustrazione riportata di seguito viene mostrata l'esecuzione simultanea di un'operazione di Garbage Collection in un thread dedicato separato.

![Thread di Garbage Collection simultanei](media/gc-concurrent.png)

## <a name="see-also"></a>Vedere anche

- [Operazione di Garbage Collection per workstation e server](workstation-server-gc.md)
- [Opzioni di configurazione in fase di esecuzione per Garbage Collection](../../core/run-time-config/garbage-collector.md)
