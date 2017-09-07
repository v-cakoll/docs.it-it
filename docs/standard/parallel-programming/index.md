---
title: Programmazione parallela in .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parallel programming
ms.assetid: 4d83c690-ad2d-489e-a2e0-b85b898a672d
caps.latest.revision: 19
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a3509229efc57b1f6b1244671df65b2f21964e65
ms.contentlocale: it-it
ms.lasthandoff: 09/05/2017

---
# <a name="parallel-programming-in-the-net-framework"></a>Programmazione parallela in .NET Framework
Un numero elevato di personal computer e workstation è dotato di due o quattro core (ovvero CPU) che consentono l'esecuzione simultanea di più thread. Ci si aspetta di qui a breve che i computer saranno dotati di un numero di core significativamente più elevato. Per sfruttare l'hardware di oggi e quello del futuro, è possibile parallelizzare il codice per distribuire il lavoro su più processori. In passato la parallelizzazione richiedeva la modifica di basso livello di thread e blocchi. [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)] e [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] migliorano il supporto per la programmazione parallela fornendo un nuovo runtime, nuovi tipi di librerie di classi e i nuovi strumenti diagnostici. Tali funzionalità semplificano lo sviluppo parallelo consentendo di scrivere codice parallelo efficiente, con granularità fine e scalabile in un linguaggio naturale senza dover usare direttamente i thread o il pool di thread. Nell'illustrazione seguente viene fornita una panoramica dettagliata dell'architettura di programmazione parallela in [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].  
  
 ![Architettura di programmazione parallela .NET](../../../docs/standard/parallel-programming/media/tpl-architecture.png "TPL_Architecture")  
  
## <a name="related-topics"></a>Argomenti correlati  
  
|Tecnologia|Descrizione|  
|----------------|-----------------|  
|[Task Parallel Library (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)|Viene fornita documentazione per la classe <xref:System.Threading.Tasks.Parallel?displayProperty=fullName> che include versioni parallele dei cicli `For` e `ForEach`, nonché per la classe <xref:System.Threading.Tasks.Task?displayProperty=fullName> che rappresenta la modalità preferita per l'espressione di operazioni asincrone.|  
|[Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)|Un'implementazione parallela di LINQ to Objects che migliora significativamente le prestazioni in molti scenari.|  
|[Strutture di dati per la programmazione in parallelo](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)|Vengono forniti collegamenti alla documentazione per classi di raccolte thread-safe, tipi di sincronizzazioni leggere e tipi per l'inizializzazione differita.|  
|[Strumenti di diagnostica in parallelo](../../../docs/standard/parallel-programming/parallel-diagnostic-tools.md)|Vengono forniti collegamenti alla documentazione per le finestre del debugger di Visual Studio per le attività e stack paralleli e il [visualizzatore di concorrenza](/visualstudio/profiling/concurrency-visualizer), che è costituito da un set di visualizzazioni nel profiler [!INCLUDE[vsprvsts](../../../includes/vsprvsts-md.md)] utilizzabili per eseguire il debug e ottimizzare le prestazioni del codice parallelo.|  
|[Partitioner personalizzati per PLINQ e TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)|Viene descritto come funzionano i partitioner e come configurare i partitioner predefiniti o creare un nuovo partitioner.|  
|[Utilità di pianificazione delle attività](http://msdn.microsoft.com/library/638f8ea5-21db-47a2-a934-86e1e961bf65)|Viene descritto come funziona l'utilità di pianificazione e come possono essere configurate le utilità di pianificazione predefinite.|  
|[Espressioni lambda in PLINQ e TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)|Viene fornita una breve panoramica delle espressioni lambda in C# e Visual Basic e ne viene mostrato l'utilizzo in PLINQ e Task Parallel Library.|  
|[Ulteriori letture](../../../docs/standard/parallel-programming/for-further-reading-parallel-programming.md)|Vengono forniti collegamenti a documentazione aggiuntiva e risorse di esempio per la programmazione parallela in .NET Framework.|  
  
## <a name="see-also"></a>Vedere anche  
 [Documento contenente una panoramica dei modelli per la programmazione parallela, ovvero come comprendere e applicare modelli paralleli con .NET Framework 4](http://go.microsoft.com/fwlink/?LinkID=185142)   
 [Esempi di programmazione parallela con .NET Framework](http://code.msdn.microsoft.com/Samples-for-Parallel-b4b76364)

