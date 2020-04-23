---
title: Garbage Collection in background
description: Informazioni sull'operazione di Garbage Collection in background in .NET e sulle differenze tra workstation e server e la procedura di Garbage Collection per workstation e server.
ms.date: 04/21/2020
helpviewer_keywords:
- garbage collection, background
- background garbage collection
ms.openlocfilehash: dcb1d348e679e07646273b8fbc4ea29b44ee4974
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82103562"
---
# <a name="background-garbage-collection"></a>Garbage Collection in background

In background garbage collection (GC), le generazioni effimere (0 e 1) vengono raccolte in base alle esigenze mentre è in corso la raccolta della generazione 2. L'operazione di Garbage Collection in background viene eseguita su uno o più thread dedicati, a seconda che si tratti di GC in background o server e si applica solo alle raccolte di generazione 2.Background garbage collection is performed on one or more dedicated threads, depending on whether it's background or server GC, and applies only to generation 2 collections.

L'operazione di Garbage Collection in background è abilitata per impostazione predefinita. Può essere abilitato o disabilitato con l'impostazione di configurazione [gcConcurrent](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) nelle app .NET Framework o l'impostazione [System.GC.Concurrent](../../core/run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent) nelle app .NET Core.

> [!NOTE]
> L'operazione di Garbage Collection in background sostituisce [l'operazione di Garbage Collection simultanea](#concurrent-garbage-collection) ed è disponibile in .NET Framework 4 e versioni successive. In .NET Framework 4 è supportato solo per l'operazione di Garbage Collection per *workstation.* A partire da .NET Framework 4.5.NET Framework 4.5, l'operazione di Garbage Collection in background è disponibile sia per le operazioni di Garbage Collection *per workstation* che per i *server.*

Una raccolta su generazioni effimere durante l'operazione di Garbage Collection in background è nota come Garbage Collection in *primo piano.* Durante l'esecuzione di un'operazione di Garbage Collection in primo piano, tutti i thread gestiti vengono sospesi.

Quando è in corso un'operazione di Garbage Collection in background e sono stati allocati un numero sufficiente di oggetti nella generazione 0, CLR esegue un'operazione di Garbage Collection in primo piano di generazione 0 o generazione 1.When background garbage collection is in progress and you've allocated enough objects in generation 0, the CLR performs a generation 0 or generation 1 foreground garbage collection. Il thread di Garbage Collection in background dedicato esegue controlli in corrispondenza di punti sicuri frequenti per stabilire se vi sia una richiesta di Garbage Collection in primo piano. In caso affermativo, la raccolta in background si autosospende in modo che possa essere eseguita l'operazione in primo piano. Al termine dell'operazione di Garbage Collection in primo piano, riprendono i thread e i thread utente dedicati di Garbage Collection in background.

La modalità in background elimina le restrizioni di allocazione imposte dalla modalità simultanea, dal momento che durante un'operazione di Garbage Collection in background è possibile eseguire operazioni temporanee. La procedura di Garbage Collection in background può rimuovere oggetti morti in generazioni effimere. Può anche espandere l'heap se necessario durante un'operazione di Garbage Collection di generazione 1.It can also expand the heap if needed during a generation 1 garbage collection.

## <a name="background-workstation-vs-server-gc"></a>Confronto tra workstation in background e catalogo globale per server

A partire da .NET Framework 4.5.NET Framework 4.5.NET Framework 4.5.NET Framework 4.5.NET Framework 4.5,00.NET Framework 4.5, background garbage collection is available for server GC. Catalogo globale in background è la modalità predefinita per l'operazione di Garbage Collection per server.

L'operazione di Garbage Collection per server in background funziona in modo simile all'operazione di Garbage Collection per workstation in background, ma esistono alcune differenze:Background server garbage collection functions similarly to background workstation garbage collection, but there are a few differences:

- L'operazione di Garbage Collection per workstation in background utilizza un thread di Garbage Collection in background dedicato, mentre l'operazione di Garbage Collection per server in background utilizza più thread. In genere, è presente un thread dedicato per ogni processore logico.

- A differenza del thread di Garbage Collection in background della workstation, non si fa eccezione ai thread GC del server in background.

Nella figura seguente viene illustrata l'operazione di Garbage Collection per workstation in background eseguita in un thread dedicato separato:The following illustration shows background *workstation* garbage collection performed on a separate, dedicated thread:

![Garbage Collection della workstation in background](./media/fundamentals/background-workstation-garbage-collection.png)

Nella figura seguente viene illustrata l'operazione di Garbage Collection per server in background eseguita in thread dedicati separati:The following illustration shows background *server* garbage collection performed on separate, dedicated threads:

![Garbage Collection del server in background](./media/fundamentals/background-server-garbage-collection.png)

## <a name="concurrent-garbage-collection"></a>Garbage Collection contemporanea

> [!TIP]
> Questa sezione si applica a:
>
> - .NET Framework 3.5 e versioni precedenti per l'operazione di Garbage Collection per workstation
> - .NET Framework 4 e versioni precedenti per l'operazione di Garbage Collection per server
>
> I rifiuti simultanei vengono sostituiti da garbage collection in background nelle versioni successive.

Nell'operazione di Garbage Collection per workstation o server è possibile [abilitare l'operazione](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md)di Garbage Collection simultanea, che consente l'esecuzione simultanea dei thread con un thread dedicato che esegue l'operazione di Garbage Collection per la maggior parte della durata dell'operazione. Questa opzione ha effetto solo sulle operazioni di Garbage Collection nella generazione 2. le generazioni 0 e 1 sono sempre non simultanee perché terminano velocemente.

La modalità simultanea consente alle applicazioni interattive una maggiore efficienza di risposta riducendo al minimo le pause di una raccolta. È possibile continuare a eseguire i thread gestiti per la maggior parte del tempo in cui viene eseguito il thread di Garbage Collection in modalità simultanea. Il risultato saranno pause più brevi durante l'esecuzione di un'operazione di Garbage Collection.

La modalità simultanea di Garbage Collection viene eseguita in un thread dedicato. Per impostazione predefinita, CLR esegue l'operazione di Garbage Collection per workstation con l'operazione di Garbage Collection simultanea abilitata sia in computer a processore singolo che a più processori.

Nell'illustrazione riportata di seguito viene mostrata l'esecuzione simultanea di un'operazione di Garbage Collection in un thread dedicato separato.

![Thread di Garbage Collection simultanei](./media/gc-concurrent.png)

## <a name="see-also"></a>Vedere anche

- [Operazione di Garbage Collection per workstation e server](workstation-server-gc.md)
- [Opzioni di configurazione in fase di esecuzione per la procedura di Garbage CollectionRun-time configuration options for garbage collection](../../core/run-time-config/garbage-collector.md)
