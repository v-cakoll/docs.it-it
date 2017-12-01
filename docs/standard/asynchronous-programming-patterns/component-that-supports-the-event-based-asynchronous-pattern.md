---
title: 'Procedura dettagliata: implementazione di un componente che supporta il modello asincrono basato su eventi'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 61f676b5-936f-40f6-83ce-f22805ec9c2f
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 150e4b27cc149774895574ddd196de5f9bc2acd8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-implementing-a-component-that-supports-the-event-based-asynchronous-pattern"></a>Procedura dettagliata: implementazione di un componente che supporta il modello asincrono basato su eventi
Se si sta scrivendo una classe con alcune operazioni che possono causare ritardi notevoli, è consigliabile assegnandogli funzionalità asincrona implementando il [Panoramica del modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).  
  
 Questa procedura dettagliata viene illustrato come creare un componente che implementa il modello asincrono basato su eventi. Viene implementato utilizzando le classi di supporto dal <xref:System.ComponentModel?displayProperty=nameWithType> spazio dei nomi, che assicura che il componente funzioni correttamente con qualsiasi modello di applicazione, tra cui [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], Console, applicazioni e le applicazioni Windows Form. Questo componente è inoltre essere progettato con una <xref:System.Windows.Forms.PropertyGrid> controllo e strumenti di progettazione personalizzate.  
  
 Durante la creazione, si disporrà di un'applicazione che consente di calcolare i numeri primi in modo asincrono. L'applicazione disporrà di un thread dell'interfaccia utente principale e un thread per ogni calcolo dei numeri primi. Anche se il test se è un numero elevato primi possono richiedere una notevole quantità di tempo, non verrà interrotto il thread dell'interfaccia utente principale per questo ritardo e il form sarà reattivo durante i calcoli. Sarà in grado di eseguire molti calcoli desiderato simultaneamente e in modo selettivo annullare i calcoli in sospeso.  
  
 Le attività illustrate nella procedura dettagliata sono le seguenti:  
  
-   Creazione del componente  
  
-   Definizione di delegati e gli eventi asincroni pubblici  
  
-   Definizione di delegati privati  
  
-   Implementazione di eventi pubblici  
  
-   Implementazione del metodo di completamento  
  
-   Implementazione dei metodi di lavoro  
  
-   Implementazione di avvio e i metodi di annullamento  
  
 Per copiare il codice in questo argomento come elenco singolo, vedere [procedura: implementare un componente che supporta il modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).  
  
## <a name="creating-the-component"></a>Creazione del componente  
 Il primo passaggio consiste nel creare il componente che consente di implementare il modello asincrono basato su eventi.  
  
#### <a name="to-create-the-component"></a>Per creare il componente  
  
-   Creare una classe denominata `PrimeNumberCalculator` che eredita da <xref:System.ComponentModel.Component>.  
  
## <a name="defining-public-asynchronous-events-and-delegates"></a>Definizione di delegati e gli eventi asincroni pubblici  
 Il componente comunica con i client che usano gli eventi. Il *NomeMetodo* `Completed` avvisa i client per il completamento di un'attività asincrona e *NomeMetodo* `ProgressChanged` evento informa dello stato di avanzamento di un'attività asincrona.  
  
#### <a name="to-define-asynchronous-events-for-clients-of-your-component"></a>Per definire gli eventi asincroni per i client del componente:  
  
1.  Importazione di <xref:System.Threading?displayProperty=nameWithType> e <xref:System.Collections.Specialized?displayProperty=nameWithType> gli spazi dei nomi nella parte superiore del file.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#11](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#11)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#11](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#11)]  
  
2.  Prima di `PrimeNumberCalculator` definizione di classe dichiarare i delegati per gli eventi di stato di avanzamento e il completamento.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#7](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#7)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#7](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#7)]  
  
3.  Nel `PrimeNumberCalculator` definizione di classe, dichiarare gli eventi per segnalare lo stato di avanzamento e completamento per i client.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#8](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#8)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#8](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#8)]  
  
4.  Dopo il `PrimeNumberCalculator` definizione di classe, derivare la `CalculatePrimeCompletedEventArgs` classe per la segnalazione sul risultato di ogni calcolo al gestore eventi del client per il `CalculatePrimeCompleted`Event. Oltre al `AsyncCompletedEventArgs` proprietà, questa classe consente al client di determinare il numero è stato testato, se si tratta di un numero primo e che cos'è il divisore prima se non è principale.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#6](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#6)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#6](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#6)]  
  
## <a name="checkpoint"></a>Checkpoint  
 A questo punto, è possibile compilare il componente.  
  
#### <a name="to-test-your-component"></a>Per testare il componente  
  
-   Compilare il componente.  
  
     Verranno visualizzati due avvisi del compilatore:  
  
    ```  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.ProgressChanged' is never used  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.CalculatePrimeCompleted' is never used  
    ```  
  
     Nella sezione successiva verranno cancellati tali avvisi.  
  
## <a name="defining-private-delegates"></a>Definizione di delegati privati  
 Gli aspetti di asincrona di `PrimeNumberCalculator` componente sono implementate internamente con un delegato speciale noto come un <xref:System.Threading.SendOrPostCallback>. Oggetto <xref:System.Threading.SendOrPostCallback> rappresenta un metodo di callback che viene eseguito in un <xref:System.Threading.ThreadPool> thread. Il metodo di callback deve avere una firma che accetta un solo parametro di tipo <xref:System.Object>, pertanto sarà necessario passare lo stato tra i delegati in una classe wrapper. Per altre informazioni, vedere <xref:System.Threading.SendOrPostCallback>.  
  
#### <a name="to-implement-your-components-internal-asynchronous-behavior"></a>Per implementare il comportamento asincrono interno del componente:  
  
1.  Dichiarare e creare il <xref:System.Threading.SendOrPostCallback> dei delegati nel `PrimeNumberCalculator` classe. Creare il <xref:System.Threading.SendOrPostCallback> gli oggetti di un metodo di utilità denominati `InitializeDelegates`.  
  
     Sono necessari due delegati: uno per i report di stato al client e uno per in fase di completamento al client.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#9](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#9)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#9](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#9)]  
    [!code-csharp[System.ComponentModel.AsyncOperationManager#20](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#20)]
    [!code-vb[System.ComponentModel.AsyncOperationManager#20](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#20)]  
  
2.  Chiamare il `InitializeDelegates` metodo nel costruttore del componente.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#21](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#21)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#21](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#21)]  
  
3.  Dichiarare un delegato di `PrimeNumberCalculator` classe che gestisce il lavoro effettivo da eseguire in modo asincrono. Questo delegato il wrapping del metodo di lavoro che controlla se un numero è primo. Il delegato accetta un <xref:System.ComponentModel.AsyncOperation> parametro, che verrà utilizzato per tenere traccia della durata dell'operazione asincrona.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#22](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#22)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#22](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#22)]  
  
4.  Creare una raccolta per la gestione di durata delle operazioni asincrone in sospeso. Il client è necessario un modo per tenere traccia delle operazioni vengono eseguite e completati e il rilevamento viene eseguito tramite la richiesta client passare un token univoco o un ID attività, quando il client effettua la chiamata al metodo asincrono. Il `PrimeNumberCalculator` componente deve tenere traccia di ogni chiamata associando l'ID attività corrispondente chiamata. Se il client passa un ID attività non è univoco, il `PrimeNumberCalculator` componente deve generare un'eccezione.  
  
     Il `PrimeNumberCalculator` componente tiene traccia dell'ID attività utilizzando una classe di raccolta speciale denominata un <xref:System.Collections.Specialized.HybridDictionary>. Nella definizione della classe, creare un <xref:System.Collections.Specialized.HybridDictionary> chiamato `userTokenToLifetime`.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#23](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#23)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#23](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#23)]  
  
## <a name="implementing-public-events"></a>Implementazione di eventi pubblici  
 I componenti che implementano il modello asincrono basato su eventi comunicano ai client mediante gli eventi. Questi eventi vengono richiamati sul thread appropriato con l'aiuto del <xref:System.ComponentModel.AsyncOperation> classe.  
  
#### <a name="to-raise-events-to-your-components-clients"></a>Per generare eventi per i client del componente:  
  
1.  Implementare gli eventi pubblici per i report ai client. È necessario un evento per segnalare lo stato di avanzamento e uno per il completamento di creazione di report.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#24](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#24)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#24](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#24)]  
  
## <a name="implementing-the-completion-method"></a>Implementazione del metodo di completamento  
 Il delegato di completamento è il metodo che verrà richiamato il comportamento sottostante, a thread libero asincrono al completamento dell'operazione asincrona per il completamento, errore o annullamento. Questa chiamata si verifica su un thread arbitrario.  
  
 Questo metodo è in un ID attività del client viene rimosso dalla raccolta interna di token client univoci. Questo metodo termina il ciclo di vita di una determinata operazione asincrona chiamando il <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> metodo sull'oggetto corrispondente <xref:System.ComponentModel.AsyncOperation>. Questa chiamata genera l'evento di completamento sul thread appropriato per il modello di applicazione. Dopo il <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> metodo viene chiamato, l'istanza di <xref:System.ComponentModel.AsyncOperation> non può più essere utilizzato, e tutti i tentativi successivi di usarlo genererà un'eccezione.  
  
 Il `CompletionMethod` firma deve contenere tutti gli stati necessari per descrivere il risultato dell'operazione asincrona. Contiene lo stato per il numero che è stato testato da questa specifica operazione asincrona, se il numero è primo e il valore del primo divisore se non è un numero primo. Contiene inoltre che descrive le eccezioni che si sono verificati, stato e <xref:System.ComponentModel.AsyncOperation> corrispondente a questa particolare attività.  
  
#### <a name="to-complete-an-asynchronous-operation"></a>Per completare un'operazione asincrona:  
  
-   Implementare il metodo di completamento. Accetta sei parametri, che viene utilizzato per popolare un `CalculatePrimeCompletedEventArgs` che viene restituito al client tramite il client `CalculatePrimeCompletedEventHandler`. L'ID attività del client viene rimosso dalla raccolta interna e termina la durata dell'operazione asincrona con una chiamata a <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A>. Il <xref:System.ComponentModel.AsyncOperation> effettua il marshalling di chiamate al thread o contesto adeguato per il modello di applicazione.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#26](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#26)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#26](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#26)]  
  
## <a name="checkpoint"></a>Checkpoint  
 A questo punto, è possibile compilare il componente.  
  
#### <a name="to-test-your-component"></a>Per testare il componente  
  
-   Compilare il componente.  
  
     Si riceverà un avviso del compilatore:  
  
    ```  
    warning CS0169: The private field 'AsynchronousPatternExample.PrimeNumberCalculator.workerDelegate' is never used  
    ```  
  
     Questo avviso verrà risolto nella sezione successiva.  
  
## <a name="implementing-the-worker-methods"></a>Implementazione dei metodi di lavoro  
 Finora è stato implementato il codice asincrono di supporto per il `PrimeNumberCalculator` componente. Ora è possibile implementare il codice che esegue il lavoro effettivo. Verranno implementati tre metodi: `CalculateWorker`, `BuildPrimeNumberList`, e `IsPrime`. Insieme, `BuildPrimeNumberList` e `IsPrime` costituiscono un noto algoritmo crivello di Eratostene, che determina se un numero è primo mediante la ricerca di tutti i numeri primi fino alla radice quadrata del numero di test. Se non vengono individuati divisori di tale punto, il numero di test è un numero primo.  
  
 Se questo componente sono state scritte per ottenere la massima efficienza, avrebbe tenuto traccia di tutti i numeri primi individuati da varie chiamate per i numeri di test diversi. È necessario anche triviali come 2, 3 e 5. Lo scopo di questo esempio è dimostrare come tempo operazioni possono essere eseguite in modo asincrono, tuttavia, in modo da queste ottimizzazioni vengono lasciate come un esercizio per l'utente.  
  
 Il `CalculateWorker` metodo viene eseguito il wrapping in un delegato e viene richiamato in modo asincrono con una chiamata a `BeginInvoke`.  
  
> [!NOTE]
>  Report di stato viene implementato nel `BuildPrimeNumberList` metodo. Nei computer veloci, `ProgressChanged` eventi possono essere generati in rapida successione. Il thread del client, in cui vengono generati, deve essere in grado di gestire questa situazione. Codice dell'interfaccia utente potrebbe essere sovraccaricato dai messaggi e non è possibile tenere il passo, giungendo. Per un esempio di interfaccia utente che gestisce questa situazione, vedere [procedura: implementare un Client del modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).  
  
#### <a name="to-execute-the-prime-number-calculation-asynchronously"></a>Per eseguire in modo asincrono il calcolo dei numeri primi:  
  
1.  Implementare il `TaskCanceled` metodo di utilità. Questo controlla la raccolta di durata di attività per l'ID attività specificato e restituisce `true` se non viene trovato l'ID attività.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#32](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#32)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#32](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#32)]  
  
2.  Implementare il metodo `CalculateWorker`. Il metodo accetta due parametri: un numero di test e un <xref:System.ComponentModel.AsyncOperation>.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#27](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#27)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#27](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#27)]  
  
3.  Implementare `BuildPrimeNumberList`. Il metodo accetta due parametri: il numero di test e un <xref:System.ComponentModel.AsyncOperation>. Usa il <xref:System.ComponentModel.AsyncOperation> per segnalare lo stato e sui risultati incrementali. Ciò assicura che i gestori di eventi del client vengono chiamati nel thread appropriato o contesto per il modello di applicazione. Quando `BuildPrimeNumberList` trova un numero primo, segnala questo come un risultato incrementale al gestore eventi del client per il `ProgressChanged` evento. È richiesta una classe derivata da <xref:System.ComponentModel.ProgressChangedEventArgs>, denominato `CalculatePrimeProgressChangedEventArgs`, che è una proprietà aggiuntiva `LatestPrimeNumber`.  
  
     Il `BuildPrimeNumberList` metodo chiama anche periodicamente il `TaskCanceled` metodo e viene chiusa se il metodo restituisce `true`.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#5)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#5)]  
  
4.  Implementare `IsPrime`. Il metodo accetta tre parametri: un elenco di numeri primi noti, il numero di test e un parametro di output per il primo divisore trovato. Dato l'elenco di numeri primi, determina se il numero di test è un numero primo.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#28](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#28)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#28](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#28)]  
  
5.  Derivare `CalculatePrimeProgressChangedEventArgs` da <xref:System.ComponentModel.ProgressChangedEventArgs>. Questa classe è necessaria per i report sui risultati incrementali al gestore eventi del client per il `ProgressChanged` evento. Contiene una proprietà aggiuntiva denominata `LatestPrimeNumber`.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#29](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#29)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#29](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#29)]  
  
## <a name="checkpoint"></a>Checkpoint  
 A questo punto, è possibile compilare il componente.  
  
#### <a name="to-test-your-component"></a>Per testare il componente  
  
-   Compilare il componente.  
  
     Gli unici elementi ancora da scrivere è i metodi di avvio e annullamento di operazioni asincrone, `CalculatePrimeAsync` e `CancelAsync`.  
  
## <a name="implementing-the-start-and-cancel-methods"></a>Implementazione dei metodi di annullamento e di avvio  
 Per avviare il metodo di lavoro nel proprio thread, è possibile chiamare `BeginInvoke` sul delegato che lo contiene. Per gestire la durata di una determinata operazione asincrona, si chiama il <xref:System.ComponentModel.AsyncOperationManager.CreateOperation%2A> metodo la <xref:System.ComponentModel.AsyncOperationManager> classe helper. Restituisce un <xref:System.ComponentModel.AsyncOperation>, che effettua il marshalling delle chiamate sui gestori di eventi del client per il thread o contesto appropriato.  
  
 Per annullare una determinata operazione in sospeso chiamando <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> sull'oggetto corrispondente <xref:System.ComponentModel.AsyncOperation>. Verrà terminata l'operazione e tutte le chiamate successive al relativo <xref:System.ComponentModel.AsyncOperation> genererà un'eccezione.  
  
#### <a name="to-implement-start-and-cancel-functionality"></a>Per implementare l'inizio e funzionalità di annullamento:  
  
1.  Implementare il metodo `CalculatePrimeAsync`. Verificare che il token fornito dal client (ID attività) sia univoco rispetto a tutti i token che rappresenta attualmente attività in sospeso. Se il client passa un token non univoco, `CalculatePrimeAsync` genera un'eccezione. In caso contrario, il token viene aggiunto alla raccolta di ID attività.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#3)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#3)]  
  
2.  Implementare il metodo `CancelAsync`. Se il `taskId` parametro esiste nella raccolta di token, viene rimosso. In questo modo non sono stata avviata l'esecuzione delle attività annullate. Se l'attività è in esecuzione, il `BuildPrimeNumberList` metodo termina quando viene rilevato che l'ID attività è stato rimosso dalla raccolta durata.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#4)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#4)]  
  
## <a name="checkpoint"></a>Checkpoint  
 A questo punto, è possibile compilare il componente.  
  
#### <a name="to-test-your-component"></a>Per testare il componente  
  
-   Compilare il componente.  
  
 Il `PrimeNumberCalculator` componente è ora completo e pronto per l'uso.  
  
 Per un client di esempio che utilizza il `PrimeNumberCalculator` componente, vedere [procedura: implementare un Client del modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).  
  
## <a name="next-steps"></a>Passaggi successivi  
 È possibile compilare questo esempio scrivendo `CalculatePrime`, l'equivalente di sincrono `CalculatePrimeAsync` metodo. In questo modo il `PrimeNumberCalculator` componente completamente compatibile con il modello asincrono basato su eventi.  
  
 In questo esempio è possibile migliorare mantenendo l'elenco di tutti i numeri primi individuati da varie chiamate per i numeri di test diversi. In questo modo, ogni attività trarranno vantaggio dal lavoro svolto dall'attività precedente. Assicurarsi di proteggere l'elenco con `lock` aree, pertanto l'accesso all'elenco da thread diversi è serializzato.  
  
 È inoltre possibile migliorare l'esempio eseguendo il test di divisori semplici, ad esempio 2, 3 e 5.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Eseguire un'operazione in background](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [Panoramica sul modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [NOT IN BUILD: Multithreading in Visual Basic](http://msdn.microsoft.com/en-us/c731a50c-09c1-4468-9646-54c86b75d269)  
 [Procedura: Implementare un componente che supporta il modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 [Programmazione multithreading con il modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)
