---
title: Programmazione parallela in .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- parallel programming
ms.assetid: 4d83c690-ad2d-489e-a2e0-b85b898a672d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2765d7bf98c8e22e0bf495ac91ab1c15327bae42
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2018
ms.locfileid: "42907979"
---
# <a name="parallel-programming-in-net"></a>Programmazione parallela in .NET

Un numero elevato di personal computer e workstation è dotato di vari core CPU che consentono l'esecuzione simultanea di più thread. Ci si aspetta di qui a breve che i computer saranno dotati di un numero di core significativamente più elevato. Per sfruttare l'hardware di oggi e quello del futuro, è possibile parallelizzare il codice per distribuire il lavoro su più processori. In passato la parallelizzazione richiedeva la modifica di basso livello di thread e blocchi. Visual Studio 2010 e .NET Framework 4 migliorano il supporto per la programmazione parallela fornendo un nuovo runtime, nuovi tipi di librerie di classi e i nuovi strumenti diagnostici. Tali funzionalità semplificano lo sviluppo parallelo consentendo di scrivere codice parallelo efficiente, con granularità fine e scalabile in un linguaggio naturale senza dover usare direttamente i thread o il pool di thread. Nell'illustrazione seguente viene fornita una panoramica dettagliata dell'architettura di programmazione parallela in .NET Framework 4.

 ![Architettura di programmazione parallela .NET](./media/tpl-architecture.png "TPL_Architecture")

## <a name="related-topics"></a>Argomenti correlati

|Tecnologia|Descrizione|
|----------------|-----------------|
|[Task Parallel Library (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)|Viene fornita documentazione per la classe <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> che include versioni parallele dei cicli `For` e `ForEach`, nonché per la classe <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> che rappresenta la modalità preferita per l'espressione di operazioni asincrone.|
|[Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)|Un'implementazione parallela di LINQ to Objects che migliora significativamente le prestazioni in molti scenari.|
|[Strutture di dati per la programmazione in parallelo](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)|Vengono forniti collegamenti alla documentazione per classi di raccolte thread-safe, tipi di sincronizzazioni leggere e tipi per l'inizializzazione differita.|
|[Strumenti di diagnostica in parallelo](../../../docs/standard/parallel-programming/parallel-diagnostic-tools.md)|Vengono forniti collegamenti alla documentazione per le finestre del debugger di Visual Studio per le attività e gli stack in parallelo e per il [Visualizzatore di concorrenza](/visualstudio/profiling/concurrency-visualizer).|
|[Partitioner personalizzati per PLINQ e TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)|Viene descritto come funzionano i partitioner e come configurare i partitioner predefiniti o creare un nuovo partitioner.|
|[Utilità di pianificazione delle attività](http://msdn.microsoft.com/library/638f8ea5-21db-47a2-a934-86e1e961bf65)|Viene descritto come funziona l'utilità di pianificazione e come possono essere configurate le utilità di pianificazione predefinite.|
|[Espressioni lambda in PLINQ e TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)|Viene fornita una breve panoramica delle espressioni lambda in C# e Visual Basic e ne viene mostrato l'utilizzo in PLINQ e Task Parallel Library.|
|[Ulteriori letture](../../../docs/standard/parallel-programming/for-further-reading-parallel-programming.md)|Vengono forniti collegamenti a informazioni aggiuntive e risorse di esempio per la programmazione parallela in .NET.|

## <a name="see-also"></a>Vedere anche

- [Panoramica della programmazione asincrona](../async.md)
- [Threading gestito](../threading/index.md)
