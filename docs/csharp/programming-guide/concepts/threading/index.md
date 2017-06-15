---
title: Threading (c#) | Documenti Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 236d157d-37c0-4ee8-89fc-721e6c596325
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: e3f213b43c2f05a5afef1db7aec8b9c2695df989
ms.contentlocale: it-it
ms.lasthandoff: 06/15/2017

---
# <a name="threading-c"></a>Threading (C#)
Threading consente al programma in c# eseguire l'elaborazione simultanea in modo che è possibile eseguire più operazioni contemporaneamente. Ad esempio, è possibile utilizzare threading per monitorare l'input dell'utente, eseguire le attività in background e gestire i flussi di input simultanei.  
  
 I thread sono le seguenti proprietà:  
  
-   I thread consentono al programma di eseguire l'elaborazione simultanea.  
  
-   .NET Framework <xref:System.Threading> dello spazio dei nomi rende più semplice l'utilizzo di thread.  
  
-   I thread condividono le risorse dell'applicazione. Per ulteriori informazioni, vedere [utilizzando thread e Threading](https://msdn.microsoft.com/library/e1dx6b2h).  
  
 Per impostazione predefinita, un programma c# dispone di un thread. Thread ausiliario, tuttavia, può essere creato e utilizzati per eseguire codice in parallelo con il thread principale. Questi thread vengono spesso denominati *thread di lavoro*.  
  
 Thread di lavoro è utilizzabile per eseguire attività di lunga o critico, senza bloccare il thread principale. Ad esempio, vengono spesso utilizzati nelle applicazioni server per soddisfare le richieste in entrata senza attendere il completamento della richiesta precedente. Thread di lavoro possono essere utilizzati anche per eseguire le attività "in background" nelle applicazioni desktop in modo che il thread principale, che guida gli elementi dell'interfaccia utente - rimane reattive alle azioni dell'utente.  
  
 Threading risolve i problemi di velocità effettiva e velocità di risposta, ma può anche causare problemi di condivisione delle risorse, ad esempio race condition e deadlock. Più thread sono ottimali per le attività che richiedono risorse diverse, ad esempio gli handle di file e le connessioni di rete. Assegnazione di più thread a una singola risorsa possono causare problemi di sincronizzazione, e se i thread bloccati durante l'attesa di altri thread di frequente vanificato lo scopo di utilizzo di più thread.  
  
 Una strategia comune consiste nell'utilizzare i thread di lavoro di eseguire richiede molto tempo o attività critiche a livello di tempo che non necessitano di molte delle risorse utilizzate da altri thread. Naturalmente, alcune risorse nel programma devono essere accessibile a più thread. In questi casi, il <xref:System.Threading> dello spazio dei nomi fornisce classi per la sincronizzazione dei thread. Tali classi includono <xref:System.Threading.Mutex>, <xref:System.Threading.Monitor>, <xref:System.Threading.Interlocked>, <xref:System.Threading.AutoResetEvent>, e <xref:System.Threading.ManualResetEvent>.  
  
 È possibile utilizzare alcune o tutte queste classi per sincronizzare le attività di più thread, ma alcune funzionalità di supporto per il threading è supportato dal linguaggio c#. Ad esempio, il [istruzione Lock](../../../../csharp/language-reference/keywords/lock-statement.md) fornisce funzionalità di sincronizzazione tramite l'utilizzo implicito di <xref:System.Threading.Monitor>.  
  
> [!NOTE]
>  A partire dal [!INCLUDE[net_v40_long](~/includes/net-v40-long-md.md)], la programmazione multithreading è notevolmente semplificata con la <xref:System.Threading.Tasks.Parallel?displayProperty=fullName> e <xref:System.Threading.Tasks.Task?displayProperty=fullName> classi, [Parallel LINQ (PLINQ)](https://msdn.microsoft.com/library/dd460688), nuove classi collection simultanee nel <xref:System.Collections.Concurrent?displayProperty=fullName> dello spazio dei nomi e un nuovo modello di programmazione che si basa sul concetto di attività, anziché i thread. Per altre informazioni, vedere [Programmazione parallela](https://msdn.microsoft.com/library/dd460693).  
  
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Descrizione|  
|-----------|-----------------|  
|[Applicazioni multithreading (C#)](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)|Viene descritto come creare e utilizzare i thread.|  
|[Parametri e valori restituiti per routine multithreading (c#)](../../../../csharp/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)|Viene descritto come passare e restituire parametri con le applicazioni con multithreading.|  
|[Procedura dettagliata: Multithreading con il componente BackgroundWorker (c#)](../../../../csharp/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md)|Viene illustrato come creare una semplice applicazione multithreading.|  
|[Sincronizzazione di thread (C#)](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)|Viene descritto come controllare le interazioni di thread.|  
|[Timer di thread (c#)](../../../../csharp/programming-guide/concepts/threading/thread-timers.md)|Viene descritto come eseguire le procedure su un thread separato a intervalli fissi.|  
|[Thread di pool (c#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md)|Viene descritto come utilizzare un pool di thread di lavoro sono gestiti dal sistema.|  
|[Procedura: utilizzare un Pool di Thread (c#)](../../../../csharp/programming-guide/concepts/threading/how-to-use-a-thread-pool.md)|Di seguito viene sincronizzato uso di più thread nel pool di thread.|  
|[Threading](https://msdn.microsoft.com/library/3e8s7xdd)|Viene descritto come implementare il threading di .NET Framework.|
