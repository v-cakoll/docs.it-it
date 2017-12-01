---
title: Thread e threading
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multiple threads
- threading [.NET Framework]
- threading [.NET Framework], multiple threads
ms.assetid: 5baac3aa-e603-4fa6-9f89-0f2c1084e6b1
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b57cac34009e13c27c6d34a0ab402f9ecbe08305
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="threads-and-threading"></a>Thread e threading
Sistemi operativi utilizzano processi per separare le varie applicazioni che sono in esecuzione. I thread sono l'unità di base in cui un sistema operativo alloca il tempo del processore, e più di un thread è possibile eseguire codice all'interno del processo. Ogni thread gestisce i gestori di eccezioni, una priorità di pianificazione e un set di strutture, che il sistema utilizzato per salvare il contesto del thread fino a quando non venga pianificata. Il contesto di thread include tutte le informazioni che necessarie per riprendere senza problemi l'esecuzione, incluse l'insieme di registri della CPU e dello stack, nello spazio degli indirizzi del processo host del thread.  
  
 .NET Framework ulteriormente suddiviso un processo del sistema operativo in sottoprocessi leggeri gestiti, definiti domini applicazione, rappresentati da <xref:System.AppDomain?displayProperty=nameWithType>. Uno o più thread gestiti (rappresentato da <xref:System.Threading.Thread?displayProperty=nameWithType>) possono essere eseguiti in uno o a qualsiasi numero di domini di applicazione all'interno dello stesso processo gestito. Sebbene ogni dominio applicazione viene avviata con un singolo thread, codice nel dominio dell'applicazione può creare thread aggiuntivi e domini applicazione aggiuntivi. Il risultato è che un thread gestito può spostare liberamente tra i domini applicazione all'interno dello stesso processo gestito; si potrebbe avere un solo thread, lo spostamento tra più domini applicazione.  
  
 Un sistema operativo che supporta il multitasking di tipo preemptive crea l'effetto dell'esecuzione simultanea di più thread da più processi. Questo avviene il tempo del processore disponibile tra i thread che ne hanno necessità di divisione, allocare un intervallo di tempo processore per ogni thread uno dopo l'altro. Il thread attualmente in esecuzione viene sospesa quando il tempo trascorso sezione e un altro thread viene ripresa l'esecuzione. Quando il sistema passa da un thread a altro, Salva il contesto del thread del thread interrotto e ricarica nel contesto del thread salvato del thread successivo nella coda di thread.  
  
 La lunghezza dell'intervallo di tempo varia a seconda del sistema operativo e processore. Poiché ogni intervallo di tempo è piccolo, più thread sembrano essere in esecuzione nello stesso momento, anche se è presente un solo processore. Questa situazione si verifica effettivamente nei sistemi multiprocessori, in cui i thread eseguibili vengono distribuiti tra i processori disponibili.  
  
## <a name="when-to-use-multiple-threads"></a>L'utilizzo di più thread  
 Software che richiede l'intervento dell'utente deve rispondere più rapidamente possibile per fornire un'esperienza utente avanzata per le attività dell'utente. Allo stesso tempo, tuttavia, dovrà eseguire i calcoli necessari per presentare i dati per l'utente più rapidamente possibile. Se l'applicazione utilizza un solo thread di esecuzione, è possibile combinare [programmazione asincrona](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md) con[.NET Framework remoting](http://msdn.microsoft.com/en-us/eccb1d31-0a22-417a-97fd-f4f1f3aa4462) o [servizi Web XML](http://msdn.microsoft.com/en-us/1e64af78-d705-4384-b08d-591a45f4379c) creati utilizzando ASP .NET per utilizzare il tempo di elaborazione di altri computer oltre a quello del proprio conto per aumentare la velocità di risposta dell'utente e diminuire il tempo di elaborazione dei dati dell'applicazione. Se si esegue il lavoro con utilizzo intensivo di input/output, è possibile utilizzare anche le porte di completamento i/o per aumentare la velocità di risposta dell'applicazione.  
  
### <a name="advantages-of-multiple-threads"></a>Vantaggi di più thread  
 Utilizzo di più di un thread, tuttavia, è la tecnica più potente disponibile per aumentare la velocità di risposta per l'utente ed elaborare i dati necessari per svolgere il lavoro quasi nello stesso momento. In un computer con un processore, più thread può creare questo effetto, sfruttando la possibilità di brevi periodi di tempo tra gli eventi utente per elaborare i dati in background. Ad esempio, un utente può modificare un foglio di calcolo mentre un altro thread è il ricalcolo di altre parti del foglio di calcolo all'interno della stessa applicazione.  
  
 Senza alcuna modifica, la stessa applicazione aumenterebbe la soddisfazione dell'utente quando viene eseguito da un computer con più processori. Il singolo dominio applicazione è possibile utilizzare più thread per eseguire le attività seguenti:  
  
-   Comunicare in rete, a un server Web e a un database.  
  
-   Eseguire operazioni che richiedono una grande quantità di tempo.  
  
-   Distinguere tra attività di priorità diverse. Ad esempio, un thread con priorità alta gestisce attività critiche a livello di tempo e un thread con priorità bassa esegue altre attività.  
  
-   Consentire l'interfaccia utente rimane attiva, durante l'allocazione di tempo di attività in background.  
  
### <a name="disadvantages-of-multiple-threads"></a>Svantaggi di più thread  
 È consigliabile utilizzare il minor numero di thread, riducendo così al minimo l'utilizzo delle risorse del sistema operativo e migliorare le prestazioni. Il threading presenta anche i requisiti di risorse e i potenziali conflitti da considerare quando si progetta un'applicazione. Come indicato di seguito sono riportati i requisiti di risorse:  
  
-   Il sistema utilizza la memoria per le informazioni di contesto richieste da processi, **AppDomain** oggetti e i thread. Pertanto, il numero di processi, **AppDomain** oggetti e i thread che è possibile creare è limitato dalla memoria disponibile.  
  
-   Tenere traccia di un numero elevato di thread utilizza intensivo del processore. Se sono presenti troppi thread, la maggior parte di essi non apporterà lo stato di avanzamento significativo. Se la maggior parte dei thread corrente sono in uno dei processi, thread di altri processi sono pianificati meno frequentemente.  
  
-   Controllo dell'esecuzione di codice con molti thread è complesso e può essere un'origine di numerosi bug.  
  
-   Distruzione di thread, è necessario sapere cosa può accadere e la gestione di tali problemi.  
  
 L'accesso condiviso alle risorse, è possibile creare conflitti. Per evitare conflitti, è necessario sincronizzare o controllare l'accesso alle risorse condivise. Errore per sincronizzare l'accesso correttamente (in domini dell'applicazione stesso o diversi) può causare problemi quali i deadlock (in cui due thread bloccarsi durante ognuna attende il completamento di altro) e (quando si verifica un risultato anomalo a causa di condizioni di competizione una dipendenza imprevista critica legata alla durata di due eventi). Il sistema fornisce gli oggetti di sincronizzazione che possono essere utilizzati per coordinare condivisione delle risorse tra più thread. Riduzione del numero di thread rende più semplice sincronizzare le risorse.  
  
 Le risorse che richiedono la sincronizzazione includono:  
  
-   Risorse di sistema (ad esempio le porte di comunicazione).  
  
-   Risorse condivise da più processi (ad esempio, gli handle di file).  
  
-   Le risorse di un singolo dominio applicazione (ad esempio globali, statici e campi di istanza) eseguito da più thread.  
  
### <a name="threading-and-application-design"></a>Threading e progettazione delle applicazioni  
 In generale, l'utilizzo di <xref:System.Threading.ThreadPool> classe è il modo più semplice per gestire più thread per attività relativamente brevi senza bloccare altri thread e quando non si prevede una specifica pianificazione delle attività. Tuttavia, esistono una serie di motivi per creare i propri thread:  
  
-   Se è necessario avere una priorità specifica un'attività.  
  
-   Se si dispone di un'attività che potrebbe richiedere molto tempo (e pertanto bloccare altre attività).  
  
-   Se è necessario inserire thread in un apartment a thread singolo (tutti **ThreadPool** thread sono in apartment con multithreading).  
  
-   Se è necessaria un'identità stabile associata al thread. Ad esempio, utilizzare un thread dedicato per la terminazione, sospeso o l'individuazione in base al nome.  
  
-   Se è necessario eseguire i thread in background che interagiscono con l'interfaccia utente, .NET Framework versione 2.0 fornisce un <xref:System.ComponentModel.BackgroundWorker> componente che comunica tramite gli eventi, con marshalling cross-thread nel thread dell'interfaccia utente.  
  
### <a name="threading-and-exceptions"></a>Threading e le eccezioni  
 Gestione delle eccezioni nel thread. Le eccezioni non gestite nei thread, anche in background, in genere termina il processo. Vi sono tre eccezioni a questa regola:  
  
-   Oggetto <xref:System.Threading.ThreadAbortException> , viene generata in un thread perché <xref:System.Threading.Thread.Abort%2A> è stato chiamato.  
  
-   Un <xref:System.AppDomainUnloadedException> , viene generata in un thread perché è in corso lo scaricamento del dominio applicazione.  
  
-   Common Language Runtime o un processo host termina il thread.  
  
 Per ulteriori informazioni, vedere [eccezioni in thread gestiti](../../../docs/standard/threading/exceptions-in-managed-threads.md).  
  
> [!NOTE]
>  Nelle versioni di .NET Framework 1.0 e 1.1, common language runtime intercetta automaticamente alcune eccezioni, ad esempio nei thread del pool. Ciò potrebbe danneggiare lo stato dell'applicazione e anche provocare il blocco delle applicazioni, che potrebbero essere molto difficile eseguire il debug.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.ThreadPool>  
 <xref:System.ComponentModel.BackgroundWorker>  
 [Sincronizzazione dei dati per il multithreading](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 [Pool di thread gestiti](../../../docs/standard/threading/the-managed-thread-pool.md)
