---
title: Thread e threading
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- multiple threads
- threading [.NET Framework]
- threading [.NET Framework], multiple threads
ms.assetid: 5baac3aa-e603-4fa6-9f89-0f2c1084e6b1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4380c509a08ebe59f9561a9e6fc596458768917f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33592184"
---
# <a name="threads-and-threading"></a>Thread e threading
I sistemi operativi si avvalgono di processi per separare le diverse applicazioni eseguite. I thread rappresentano l'unità di base a cui un sistema operativo assegna il tempo del processore ed è possibile che più di un thread esegua porzioni di codice all'interno del processo. Ogni thread gestisce gestori di eccezioni, una priorità di pianificazione e un insieme di strutture usate dal sistema per salvare il contesto del thread fino a quando viene pianificato. Nel contesto del thread sono presenti tutte le informazioni necessarie per riprendere senza problemi l'esecuzione nello spazio degli indirizzi del processo host del thread, incluso l'insieme di registri della CPU e lo stack.  
  
 In .NET Framework un processo di un sistema operativo viene suddiviso ulteriormente in sottoprocessi leggeri gestiti, definiti domini dell'applicazione e rappresentati da <xref:System.AppDomain?displayProperty=nameWithType>. Uno o più thread gestiti, rappresentati da <xref:System.Threading.Thread?displayProperty=nameWithType>, possono essere eseguiti in uno o in un numero indefinito di domini dell'applicazione all'interno dello stesso processo gestito. Sebbene ogni dominio dell'applicazione sia avviato con un singolo thread, il codice in quel dominio può creare domini dell'applicazione e thread aggiuntivi. Il risultato è che un thread gestito può spostarsi senza problemi da un dominio dell'applicazione all'altro all'interno dello stesso processo gestito; è possibile avere anche un solo thread che si sposta tra diversi domini dell'applicazione.  
  
 Un sistema operativo che supporta il multitasking di tipo preemptive crea l'effetto dell'esecuzione simultanea di più thread di più processi. Questa operazione viene eseguita dividendo il tempo del processore disponibile tra i thread che lo richiedono e allocando una porzione di tempo del processore a ogni thread, uno dopo l'altro. Il thread in quel momento in esecuzione viene sospeso allo scadere della porzione di tempo e viene ripresa l'esecuzione di un altro thread. Quando il sistema passa da un thread all'altro, salva il contesto del thread interrotto e ricarica il contesto del thread salvato del thread successivo nell'apposita coda.  
  
 L'entità della porzione di tempo dipende dal sistema operativo e dal processore. Dal momento che ogni porzione di tempo è limitata, più thread sembrano contemporaneamente in esecuzione, anche in presenza di un solo processore. Questa situazione si verifica essenzialmente nei sistemi a più processori, in cui i thread eseguibili vengono distribuiti tra i vari processori disponibili.  
  
## <a name="when-to-use-multiple-threads"></a>Utilizzo di più thread  
 I programmi software che richiedono l'interazione dell'utente devono garantire tempi di risposta rapidi per offrire un'esperienza soddisfacente ed eseguire al tempo stesso i calcoli necessari per presentare all'utente i dati il più velocemente possibile. Se l'applicazione usa un solo thread di esecuzione, è possibile combinare la [programmazione asincrona](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md) con i [servizi remoti di .NET Framework](https://msdn.microsoft.com/library/eccb1d31-0a22-417a-97fd-f4f1f3aa4462) o i [servizi Web XML](https://msdn.microsoft.com/library/1e64af78-d705-4384-b08d-591a45f4379c) creati mediante ASP.NET per usare il tempo di elaborazione di altri computer, oltre a quello già disponibile per aumentare i tempi di risposta all'utente e diminuire il tempo di elaborazione dei dati dell'applicazione. Se si eseguono molte operazioni di input/output, sarà possibile anche usare le porte di completamento di I/O per aumentare la velocità di risposta dell'applicazione.  
  
### <a name="advantages-of-multiple-threads"></a>Vantaggi dei thread multipli  
 L'utilizzo di più thread rappresenta la tecnica più efficace attualmente disponibile per aumentare la velocità di risposta ed elaborare i dati necessari per completare il lavoro quasi contemporaneamente. In un computer dotato di un solo processore, questo effetto viene ottenuto da più thread, che sfruttano i brevi periodi di tempo tra un evento utente e l'altro per l'elaborazione dei dati in background. Un utente può modificare, ad esempio, un foglio di calcolo mentre un altro thread ne ricalcola altre parti all'interno della stessa applicazione.  
  
 Senza alcuna modifica, la stessa applicazione aumenterebbe in modo significativo la soddisfazione del cliente se eseguita in un computer con più processori. Il singolo dominio dell'applicazione potrebbe usare più thread per eseguire le attività seguenti:  
  
-   Comunicare in rete con un server Web e un database.  
  
-   Eseguire operazioni che richiedono una notevole quantità di tempo.  
  
-   Operare una distinzione tra attività con diversa priorità. Un thread ad alta priorità, ad esempio, gestisce attività in cui il tempo riveste molta importanza mentre un'attività a bassa priorità ne esegue altre.  
  
-   Consentire all'interfaccia utente di continuare ad essere veloce, allocando più tempo alle attività in background.  
  
### <a name="disadvantages-of-multiple-threads"></a>Svantaggi dei thread multipli  
 Si consiglia di usare il minor numero di thread possibile, in modo da ridurre al minimo l'utilizzo delle risorse del sistema operativo e migliorare le prestazioni. Il threading presenta anche requisiti in termini di risorse e potenziali conflitti da considerare in fase di progettazione dell'applicazione. Di seguito sono elencati i requisiti in termini di risorse:  
  
-   Il sistema consuma memoria per le informazioni sul contesto richieste da processi, oggetti **AppDomain** e thread. Il numero di processi, oggetti **AppDomain** e thread che è possibile creare, quindi, è limitato dalla memoria disponibile.  
  
-   Tenere traccia di un numero elevato di thread determina un consumo significativo di tempo del processore. Se sono presenti troppi thread, solo alcuni progrediranno in modo significativo. Se la maggior parte dei thread correnti si trova in un processo, quelli contenuti in altri processi vengono pianificati meno frequentemente.  
  
-   Il controllo dell'esecuzione del codice con molti thread è un'operazione complessa e può causare numerosi bug.  
  
-   La distruzione dei thread richiede la conoscenza dei possibili effetti e la capacità di gestire i problemi creati.  
  
 L'accesso condiviso alle risorse può creare conflitti. Per evitarli, è necessario sincronizzare o controllare l'accesso alle risorse condivise. Una non corretta sincronizzazione dell'accesso, in domini dell'applicazione medesimi o diversi, può determinare problemi quali deadlock (in cui due thread non rispondono più mentre l'uno attende il completamento dell'altro) e race condition (quando un risultato anomalo si verifica a causa di una dipendenza critica imprevista legata alla durata di due eventi). Nel sistema vengono forniti oggetti di sincronizzazione che è possibile usare per coordinare la condivisione delle risorse tra più thread. La riduzione del numero di thread rende più semplice la sincronizzazione delle risorse.  
  
 Le risorse che richiedono la sincronizzazione includono:  
  
-   Risorse di sistema, come le porte di comunicazione.  
  
-   Risorse condivise da più processi, come gli handle dei file.  
  
-   Risorse di un singolo dominio dell'applicazione, ad esempio campi globali, statici e di istanza, a cui accedono più thread.  
  
### <a name="threading-and-application-design"></a>Threading e progettazione delle applicazioni  
 In generale, l'utilizzo della classe <xref:System.Threading.ThreadPool> rappresenta il modo più semplice per gestire più thread per attività relativamente brevi senza bloccare altri thread e quando non si prevede una specifica pianificazione delle attività. Esistono tuttavia vari motivi per cui è opportuno creare thread personalizzati:  
  
-   Se è necessario che un'attività abbia una determinata priorità.  
  
-   Se si dispone di un'attività che potrebbe richiedere molto tempo, bloccandone quindi altre.  
  
-   Se è necessario inserire dei thread in un apartment a singolo thread. Tutti i thread **ThreadPool** sono in apartment con multithreading.  
  
-   Se è necessaria un'identità stabile associata al thread. È opportuno ad esempio usare un thread dedicato per terminarlo, sospenderlo o individuarlo in base al nome.  
  
-   Se è necessario eseguire thread in background che interagiscono con l'interfaccia utente, in .NET Framework versione 2.0 è disponibile un componente <xref:System.ComponentModel.BackgroundWorker> che comunica tramite eventi, con marshalling cross-thread nel thread dell'interfaccia utente.  
  
### <a name="threading-and-exceptions"></a>Threading ed eccezioni  
 Gestire le eccezioni nei thread. In genere, le eccezioni non gestite nei thread, anche in background, determinano l'interruzione del processo. Vi sono tre eccezioni a questa regola:  
  
-   Viene generata un'eccezione <xref:System.Threading.ThreadAbortException> in un thread perché è stato chiamato il metodo <xref:System.Threading.Thread.Abort%2A>.  
  
-   Viene generata un'eccezione <xref:System.AppDomainUnloadedException> in un thread perché è in corso lo scaricamento del dominio dell'applicazione.  
  
-   Common Language Runtime o un processo host termina il thread.  
  
 Per altre informazioni, vedere [Eccezioni in thread gestiti](../../../docs/standard/threading/exceptions-in-managed-threads.md).  
  
> [!NOTE]
>  In .NET Framework versioni 1.0 e 1.1, Common Language Runtime intercetta automaticamente alcune eccezioni, ad esempio nei thread di un pool. Questo comportamento può danneggiare lo stato dell'applicazione e determinare il blocco delle applicazioni, rendendo particolarmente difficile il debug.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.ThreadPool>  
 <xref:System.ComponentModel.BackgroundWorker>  
 [Sincronizzazione dei dati per il multithreading](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 [Pool di thread gestiti](../../../docs/standard/threading/the-managed-thread-pool.md)
