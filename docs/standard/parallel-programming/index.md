---
title: Programmazione parallela in .NET
ms.date: 09/12/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- parallel programming
ms.assetid: 4d83c690-ad2d-489e-a2e0-b85b898a672d
ms.openlocfilehash: 7adc37374876ebe4dd47e30afa06b5199f34dad5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290694"
---
# <a name="parallel-programming-in-net"></a>Programmazione parallela in .NET

Un numero elevato di personal computer e workstation è dotato di diversi core CPU che consentono l'esecuzione simultanea di più thread. Per sfruttare l'hardware, è possibile parallelizzare il codice per distribuire il lavoro su più processori.

In passato la parallelizzazione richiedeva la modifica di basso livello di thread e blocchi. Visual Studio e .NET Framework migliorano il supporto per la programmazione parallela fornendo un runtime, tipi di librerie di classi e strumenti diagnostici. Queste funzionalità che sono state introdotte con .NET Framework 4, semplificano lo sviluppo parallelo. È possibile scrivere codice parallelo efficiente, con granularità fine e scalabile in un linguaggio naturale senza dover usare direttamente i thread o il pool di thread.

Nell'illustrazione seguente viene fornita una panoramica dettagliata dell'architettura di programmazione parallela in .NET Framework:

![Architettura di programmazione parallela .NET](./media/tpl-architecture.png)

## <a name="related-topics"></a>Argomenti correlati

|Tecnologia|Descrizione|
|----------------|-----------------|
|[Task Parallel Library (TPL)](task-parallel-library-tpl.md)|Viene fornita documentazione per la classe <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> che include versioni parallele dei cicli `For` e `ForEach`, nonché per la classe <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> che rappresenta la modalità preferita per l'espressione di operazioni asincrone.|
|[Parallel LINQ (PLINQ)](introduction-to-plinq.md)|Un'implementazione parallela di LINQ to Objects che migliora significativamente le prestazioni in molti scenari.|
|[Strutture di dati per la programmazione parallela](data-structures-for-parallel-programming.md)|Vengono forniti collegamenti alla documentazione per classi di raccolte thread-safe, tipi di sincronizzazioni leggere e tipi per l'inizializzazione differita.|
|[Strumenti di diagnostica parallela](parallel-diagnostic-tools.md)|Vengono forniti collegamenti alla documentazione per le finestre del debugger di Visual Studio per le attività e gli stack in parallelo e per il [Visualizzatore di concorrenza](/visualstudio/profiling/concurrency-visualizer).|
|[Partitioner personalizzati per PLINQ e TPL](custom-partitioners-for-plinq-and-tpl.md)|Viene descritto come funzionano i partitioner e come configurare i partitioner predefiniti o creare un nuovo partitioner.|
|[Utilità di pianificazione delle attività](xref:System.Threading.Tasks.TaskScheduler)|Viene descritto come funziona l'utilità di pianificazione e come possono essere configurate le utilità di pianificazione predefinite.|
|[Espressioni lambda in PLINQ e TPL](lambda-expressions-in-plinq-and-tpl.md)|Viene fornita una breve panoramica delle espressioni lambda in C# e Visual Basic e ne viene mostrato l'utilizzo in PLINQ e Task Parallel Library.|
|[Per ulteriori informazioni](for-further-reading-parallel-programming.md)|Vengono forniti collegamenti a informazioni aggiuntive e risorse di esempio per la programmazione parallela in .NET.|

## <a name="see-also"></a>Vedere anche

- [Panoramica della programmazione asincrona](../async.md)
- [Threading gestito](../threading/index.md)
