---
title: Threading (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 704bb04b-ff23-471d-ab12-3cec1c2bca59
ms.openlocfilehash: 366c88db5d229120b1e626f275b4eeb8ecd42dba
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2018
ms.locfileid: "48844995"
---
# <a name="threading-visual-basic"></a>Threading (Visual Basic)
Il threading consente al programma Visual Basic di attivare l'elaborazione simultanea per eseguire più operazioni contemporaneamente. Ad esempio, è possibile usare il threading per monitorare l'input dell'utente, eseguire attività in background e gestire flussi di input simultanei.  
  
 I thread hanno le caratteristiche seguenti:  
  
-   Consentono al programma di eseguire elaborazioni simultanee.  
  
-   Possono essere usati facilmente grazie allo spazio dei nomi <xref:System.Threading> di .NET Framework.  
  
-   Condividono le risorse dell'applicazione. Per altre informazioni, vedere [Uso di thread e threading](../../../../standard/threading/using-threads-and-threading.md).  
  
 Per impostazione predefinita un programma Visual Basic ha un solo thread. È possibile tuttavia creare thread ausiliari da usare per eseguire il codice in parallelo al thread primario. Questi thread sono spesso chiamati *thread di lavoro*.  
  
 I thread di lavoro possono essere usati per eseguire attività lunghe e con tempi critici senza sovraccaricare il thread primario. Ad esempio, i thread di lavoro vengono spesso usati nelle applicazioni server per soddisfare le richieste in arrivo senza attendere il completamento della richiesta precedente. I thread di lavoro vengono usati anche per eseguire attività in background nelle applicazioni desktop, in modo tale che il thread principale, che gestisce gli elementi dell'interfaccia utente, garantisca tempi di risposta ottimali per le azioni dell'utente.  
  
 Il threading consente di risolvere i problemi legati alla velocità effettiva e alla velocità di risposta, ma può comportare problemi di condivisione delle risorse, quali deadlock e race condition. L'uso di più thread è consigliato per le attività che richiedono risorse differenti, ad esempio handle di file e connessioni di rete. L'assegnazione di più thread a un'unica risorsa potrebbe generare errori di sincronizzazione e se i thread vengono bloccati di frequente in attesa di altri thread lo scopo del multithreading risulta vanificato.  
  
 Una strategia comune consiste nell'usare i thread di lavoro per eseguire attività lunghe o con tempi critici ma che non richiedono molte delle risorse usate da altri thread. È necessario, naturalmente, che ad alcune risorse del programma accedano più thread. In questi casi, lo spazio dei nomi <xref:System.Threading> offre le classi per la sincronizzazione dei thread. Queste classi includono <xref:System.Threading.Mutex>, <xref:System.Threading.Monitor>, <xref:System.Threading.Interlocked>, <xref:System.Threading.AutoResetEvent> e <xref:System.Threading.ManualResetEvent>.  
  
 È possibile usare alcune o tutte queste classi per sincronizzare le attività di più thread, ma il supporto per il threading viene offerto in parte dal linguaggio Visual Basic. Ad esempio, l'[istruzione SyncLock](../../../../visual-basic/language-reference/statements/synclock-statement.md) offre funzionalità di sincronizzazione attraverso l'uso implicito di <xref:System.Threading.Monitor>.  
  
> [!NOTE]
>  A partire da [!INCLUDE[net_v40_long](~/includes/net-v40-long-md.md)], la programmazione multithreading è notevolmente semplificata con le classi <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, [Parallel LINQ (PLINQ)](../../../../standard/parallel-programming/parallel-linq-plinq.md), le nuove classi di raccolta simultanee nello spazio dei nomi <xref:System.Collections.Concurrent?displayProperty=nameWithType> e un nuovo modello di programmazione che si basa sul concetto di attività anziché di thread. Per altre informazioni, vedere [Programmazione parallela](../../../../standard/parallel-programming/index.md).  
  
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Descrizione|  
|-----------|-----------------|  
|[Threading](../../../../standard/threading/index.md)|Descrive come implementare il threading in .NET Framework.|
