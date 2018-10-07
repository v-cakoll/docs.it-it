---
title: Threading (C#)
ms.date: 07/20/2015
ms.assetid: 236d157d-37c0-4ee8-89fc-721e6c596325
ms.openlocfilehash: c90816a14bfbcd2ddd469c1240e94d99bfbbb5e5
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2018
ms.locfileid: "48844878"
---
# <a name="threading-c"></a>Threading (C#)
Il threading consente al programma C# di eseguire l'elaborazione simultanea in modo che sia possibile eseguire più operazioni contemporaneamente. Ad esempio, è possibile usare il threading per monitorare l'input dell'utente, eseguire attività in background e gestire flussi di input simultanei.  
  
 I thread hanno le caratteristiche seguenti:  
  
-   Consentono al programma di eseguire elaborazioni simultanee.  
  
-   Possono essere usati facilmente grazie allo spazio dei nomi <xref:System.Threading> di .NET Framework.  
  
-   Condividono le risorse dell'applicazione. Per altre informazioni, vedere [Uso di thread e threading](../../../../../docs/standard/threading/using-threads-and-threading.md).  
  
 Per impostazione predefinita, un programma C# ha un solo thread. È possibile tuttavia creare thread ausiliari da usare per eseguire il codice in parallelo al thread primario. Questi thread sono spesso chiamati *thread di lavoro*.  
  
 I thread di lavoro possono essere usati per eseguire attività lunghe e con tempi critici senza sovraccaricare il thread primario. Ad esempio, i thread di lavoro vengono spesso usati nelle applicazioni server per soddisfare le richieste in arrivo senza attendere il completamento della richiesta precedente. I thread di lavoro vengono usati anche per eseguire attività in background nelle applicazioni desktop, in modo tale che il thread principale, che gestisce gli elementi dell'interfaccia utente, garantisca tempi di risposta ottimali per le azioni dell'utente.  
  
 Il threading consente di risolvere i problemi legati alla velocità effettiva e alla velocità di risposta, ma può comportare problemi di condivisione delle risorse, quali deadlock e race condition. L'uso di più thread è consigliato per le attività che richiedono risorse differenti, ad esempio handle di file e connessioni di rete. L'assegnazione di più thread a un'unica risorsa potrebbe generare errori di sincronizzazione e se i thread vengono bloccati di frequente in attesa di altri thread lo scopo del multithreading risulta vanificato.  
  
 Una strategia comune consiste nell'usare i thread di lavoro per eseguire attività lunghe o con tempi critici ma che non richiedono molte delle risorse usate da altri thread. È necessario, naturalmente, che ad alcune risorse del programma accedano più thread. In questi casi, lo spazio dei nomi <xref:System.Threading> offre le classi per la sincronizzazione dei thread. Queste classi includono <xref:System.Threading.Mutex>, <xref:System.Threading.Monitor>, <xref:System.Threading.Interlocked>, <xref:System.Threading.AutoResetEvent> e <xref:System.Threading.ManualResetEvent>.  
  
 È possibile usare alcune o tutte queste classi per sincronizzare le attività di più thread, ma il supporto per il threading viene offerto in parte dal linguaggio C#. Ad esempio, l'[istruzione Lock](../../../../csharp/language-reference/keywords/lock-statement.md) offre le funzionalità di sincronizzazione attraverso l'uso implicito di <xref:System.Threading.Monitor>.  
  
> [!NOTE]
>  A partire da [!INCLUDE[net_v40_long](~/includes/net-v40-long-md.md)], la programmazione multithreading è notevolmente semplificata con le classi <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, [Parallel LINQ (PLINQ)](../../../../standard/parallel-programming/parallel-linq-plinq.md), le nuove classi di raccolta simultanee nello spazio dei nomi <xref:System.Collections.Concurrent?displayProperty=nameWithType> e un nuovo modello di programmazione che si basa sul concetto di attività anziché di thread. Per altre informazioni, vedere [Programmazione parallela](../../../../../docs/standard/parallel-programming/index.md).  
  
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Descrizione|  
|-----------|-----------------|  
|[Threading](../../../../../docs/standard/threading/index.md)|Descrive come implementare il threading in .NET Framework.|
