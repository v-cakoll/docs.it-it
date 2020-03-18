---
title: 'Procedura: implementare un componente che supporta il modello asincrono basato su eventi'
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: 44a1019ac8169138aa95b03e2027d9539cbf8391
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "71957362"
---
# <a name="how-to-implement-a-component-that-supports-the-event-based-asynchronous-pattern"></a>Procedura: implementare un componente che supporta il modello asincrono basato su eventi
In caso di scrittura di una classe con alcune operazioni che possono causare ritardi notevoli, è consigliabile assegnare la funzionalità asincrona implementando [Panoramica sul modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).  
  
 Questa procedura dettagliata illustra come creare un componente che implementa un modello asincrono basato su eventi. L'implementazione viene eseguita usando classi helper dallo spazio dei nomi <xref:System.ComponentModel?displayProperty=nameWithType>, per poter assicurare che il componente funzioni correttamente con qualsiasi modello di applicazione, tra cui ASP.NET, applicazioni console e applicazioni Windows Form. Questo componente è anche identificabile da un controllo <xref:System.Windows.Forms.PropertyGrid> e dalle finestre di progettazione personalizzate.  
  
 Nel corso della procedura, un'applicazione calcola i numeri primi in modo asincrono. L'applicazione avrà un thread di interfaccia utente principale e un thread per ogni calcolo di numero primo. Anche se verificare che un numero a molte cifre sia un numero primo può richiedere una notevole quantità di tempo, il thread principale dell'interfaccia utente non verrà interrotto da questa operazione e la capacità di risposta del form resterà inalterata durante i calcoli. Sarà possibile eseguire simultaneamente tutti i calcoli necessari e annullare in modo selettivo i calcoli in sospeso.  
  
 Le attività illustrate nella procedura dettagliata sono le seguenti:  
  
- Creazione del componente  
  
- Definizione di delegati ed eventi asincroni pubblici  
  
- Definizione di delegati privati  
  
- Implementazione di eventi pubblici  
  
- Implementazione del metodo di completamento  
  
- Implementazione dei metodi di lavoro  
  
- Implementazione dei metodi di avvio e di annullamento  
  
 Per copiare il codice in questo argomento come singolo listato, vedere [Procedura: Implementare un client del modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).  
  
## <a name="creating-the-component"></a>Creazione del componente  
 Il primo passaggio prevede la creazione del componente che implementerà il modello asincrono basato su eventi.  
  
### <a name="to-create-the-component"></a>Per creare il componente  
  
- Creare una classe denominata `PrimeNumberCalculator` che eredita da <xref:System.ComponentModel.Component>.  
  
## <a name="defining-public-asynchronous-events-and-delegates"></a>Definizione di delegati ed eventi asincroni pubblici  
 Il componente comunica con i client usando gli eventi. L'evento _MethodName_**Completed** avvisa i client del completamento di un'attività asincrona, mentre l'evento _MethodName_**ProgressChanged** li informa dello stato di avanzamento di questa attività.  
  
### <a name="to-define-asynchronous-events-for-clients-of-your-component"></a>Per definire gli eventi asincroni per i client del componente:  
  
1. Importare gli spazi dei nomi <xref:System.Threading?displayProperty=nameWithType> e <xref:System.Collections.Specialized?displayProperty=nameWithType> all'inizio del file.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#11](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#11)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#11](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#11)]  
  
2. Prima della definizione della classe `PrimeNumberCalculator` dichiarare i delegati per gli eventi di stato e di completamento.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#7](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#7)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#7](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#7)]  
  
3. Nella definizione della classe `PrimeNumberCalculator` dichiarare gli eventi per segnalare ai client lo stato e il completamento.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#8](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#8)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#8](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#8)]  
  
4. Dopo la definizione della classe `PrimeNumberCalculator`, derivare la classe `CalculatePrimeCompletedEventArgs` per segnalare l'esito di ogni calcolo al gestore eventi del client per l'evento `CalculatePrimeCompleted`. Oltre alle proprietà `AsyncCompletedEventArgs`, questa classe consente al client di determinare quale numero è stato testato, se è un numero primo e qual è il primo divisore se non è un numero primo.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#6](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#6)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#6](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#6)]  
  
## <a name="checkpoint"></a>Checkpoint  
 A questo punto, è possibile compilare il componente.  
  
### <a name="to-test-your-component"></a>Per eseguire il test del componente  
  
- Compilare il componente.  
  
     Verranno visualizzati due avvisi del compilatore:  
  
    ```console  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.ProgressChanged' is never used  
    warning CS0067: The event 'AsynchronousPatternExample.PrimeNumberCalculator.CalculatePrimeCompleted' is never used  
    ```  
  
     Questi avvisi verranno cancellati nella sezione successiva.  
  
## <a name="defining-private-delegates"></a>Definizione di delegati privati  
 Gli aspetti asincroni del componente `PrimeNumberCalculator` vengono implementati internamente con uno speciale delegato noto come <xref:System.Threading.SendOrPostCallback>. Un delegato <xref:System.Threading.SendOrPostCallback> rappresenta un metodo di callback eseguito su un thread <xref:System.Threading.ThreadPool>. Il metodo di callback deve avere una firma che accetta un singolo parametro di tipo <xref:System.Object> e sarà quindi necessario passare lo stato tra i delegati in una classe wrapper. Per altre informazioni, vedere <xref:System.Threading.SendOrPostCallback>.  
  
### <a name="to-implement-your-components-internal-asynchronous-behavior"></a>Per implementare il comportamento asincrono interno del componente:  
  
1. Dichiarare e creare i delegati <xref:System.Threading.SendOrPostCallback> nella classe `PrimeNumberCalculator`. Creare gli oggetti <xref:System.Threading.SendOrPostCallback> in un metodo di utilità denominato `InitializeDelegates`.  
  
     Saranno necessari due delegati: uno per segnalare lo stato al client e uno per segnalare il completamento al client.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#9](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#9)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#9](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#9)]  
    [!code-csharp[System.ComponentModel.AsyncOperationManager#20](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#20)]
    [!code-vb[System.ComponentModel.AsyncOperationManager#20](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#20)]  
  
2. Chiamare il metodo `InitializeDelegates` nel costruttore del componente.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#21](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#21)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#21](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#21)]  
  
3. Dichiarare un delegato nella classe `PrimeNumberCalculator` che gestisce il lavoro effettivo da eseguire in modo asincrono. Questo delegato esegue il wrapping del metodo di lavoro che verifica se un numero è primo. Il delegato accetta un parametro <xref:System.ComponentModel.AsyncOperation>, che verrà usato per tenere traccia della durata dell'operazione asincrona.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#22](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#22)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#22](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#22)]  
  
4. Creare una raccolta per la gestione delle durate delle operazioni asincrone in sospeso. Il client deve poter tenere traccia delle operazioni mentre vengono eseguite e completate e, a questo scopo, si richiede al client di passare un token univoco, ovvero un ID attività, quando il client effettua la chiamata al metodo asincrono. Il componente `PrimeNumberCalculator` deve tenere traccia di ogni chiamata associando l'ID attività alla chiamata corrispondente. Se il client passa un ID attività non univoco, il componente `PrimeNumberCalculator` deve generare un'eccezione.  
  
     Il componente `PrimeNumberCalculator` tiene traccia dell'ID attività usando una speciale classe di raccolta denominata <xref:System.Collections.Specialized.HybridDictionary>. Nella definizione della classe creare una classe <xref:System.Collections.Specialized.HybridDictionary> denominata `userTokenToLifetime`.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#23](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#23)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#23](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#23)]  
  
## <a name="implementing-public-events"></a>Implementazione di eventi pubblici  
 I componenti che implementano il modello asincrono basato su eventi comunicano con i client usando gli eventi. Questi eventi vengono richiamati sul thread appropriato grazie alla classe <xref:System.ComponentModel.AsyncOperation>.  
  
### <a name="to-raise-events-to-your-components-clients"></a>Per generare eventi per i client del componente:  
  
1. Implementare gli eventi pubblici per la segnalazione ai client. Saranno necessari un evento per segnalare lo stato e uno per segnalare il completamento.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#24](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#24)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#24](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#24)]  
  
## <a name="implementing-the-completion-method"></a>Implementazione del metodo di completamento  
 Il delegato di completamento è il metodo che verrà richiamato dal comportamento asincrono a thread libero sottostante quando l'operazione asincrona terminerà con completamento corretto, errore o annullamento. Questa chiamata si verifica su un thread arbitrario.  
  
 È in questo metodo che l'ID attività del client viene rimosso dalla raccolta interna di token client univoci. Questo metodo termina anche la durata di una determinata operazione asincrona chiamando il metodo <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> sulla classe <xref:System.ComponentModel.AsyncOperation> corrispondente. Questa chiamata genera l'evento di completamento nel thread appropriato per il modello di applicazione. Dopo la chiamata al metodo <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A>, questa istanza di <xref:System.ComponentModel.AsyncOperation> non può più essere usata ed eventuali tentativi successivi di usarla genereranno un'eccezione.  
  
 La firma `CompletionMethod` deve contenere tutti gli stati necessari per descrivere l'esito dell'operazione asincrona. Contiene lo stato per il numero testato da questa particolare operazione asincrona, lo stato che indica se il numero è primo e il valore del primo divisore se non è un numero primo. Contiene anche lo stato che descrive eventuali eccezioni generate e la classe <xref:System.ComponentModel.AsyncOperation> corrispondente a questa particolare attività.  
  
### <a name="to-complete-an-asynchronous-operation"></a>Per completare un'operazione asincrona:  
  
- Implementare il metodo di completamento. Accetta sei parametri, che usa per popolare `CalculatePrimeCompletedEventArgs` restituito al client tramite `CalculatePrimeCompletedEventHandler` del client. Rimuove il token ID attività del client dalla raccolta interna e termina la durata dell'operazione asincrona con una chiamata a <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A>. <xref:System.ComponentModel.AsyncOperation> effettua il marshalling della chiamata al thread o al contesto adeguato al modello di applicazione.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#26](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#26)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#26](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#26)]  
  
## <a name="checkpoint"></a>Checkpoint  
 A questo punto, è possibile compilare il componente.  
  
### <a name="to-test-your-component"></a>Per eseguire il test del componente  
  
- Compilare il componente.  
  
     Verrà visualizzato un avviso del compilatore:  
  
    ```console  
    warning CS0169: The private field 'AsynchronousPatternExample.PrimeNumberCalculator.workerDelegate' is never used  
    ```  
  
     Questo avviso verrà risolto nella sezione successiva.  
  
## <a name="implementing-the-worker-methods"></a>Implementazione dei metodi di lavoro  
 Fino a questo punto, è stato implementato il codice asincrono di supporto per il componente `PrimeNumberCalculator`. È ora possibile implementare il codice che esegue il lavoro effettivo. Si implementeranno tre metodi: `CalculateWorker`, `BuildPrimeNumberList` e `IsPrime`. `BuildPrimeNumberList` e `IsPrime` costituiscono un noto algoritmo chiamato Crivello di Eratostene, che determina se un numero è primo trovando tutti i numeri primi fino alla radice quadrata del numero di test. Se entro quel punto non vengono trovati divisori, il numero di test è un numero primo.  
  
 Se questo componente fosse davvero efficiente, memorizzerebbe tutti i numeri primi individuati dalle varie chiamate per i diversi numeri di test. Cercherebbe anche i divisori irrilevanti, ad esempio 2, 3 e 5. Lo scopo di questo esempio è tuttavia dimostrare come le operazioni che richiedono molto tempo possono essere eseguite in modo asincrono, quindi queste ottimizzazioni possono diventare il tema di un esercizio per l'utente.  
  
 Il metodo `CalculateWorker` viene sottoposto a wrapping in un delegato e richiamato in modo asincrono con una chiamata a `BeginInvoke`.  
  
> [!NOTE]
> Il report dello stato viene implementato nel metodo `BuildPrimeNumberList`. Nei computer veloci gli eventi `ProgressChanged` possono essere generati in rapida successione. Il thread del client, in cui questi eventi vengono generati, deve poter gestire questa situazione. Il codice dell'interfaccia utente potrebbe non riuscire a stare al passo perché sommerso di messaggi e di conseguenza bloccarsi. Per un'interfaccia utente di esempio che gestisce questa situazione, vedere [Procedura: Implementare un client del modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).  
  
### <a name="to-execute-the-prime-number-calculation-asynchronously"></a>Per eseguire in modo asincrono il calcolo dei numeri primi:  
  
1. Implementare il metodo di utilità `TaskCanceled`, che controlla la raccolta della durata dell'attività per l'ID attività specificato e restituisce `true` se l'ID attività non viene trovato.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#32](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#32)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#32](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#32)]  
  
2. Implementare il metodo `CalculateWorker`. Accetta due parametri: un numero da testare e una classe <xref:System.ComponentModel.AsyncOperation>.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#27](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#27)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#27](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#27)]  
  
3. Implementare `BuildPrimeNumberList`. Accetta due parametri: il numero da testare e una classe <xref:System.ComponentModel.AsyncOperation>. Usa la classe <xref:System.ComponentModel.AsyncOperation> per segnalare lo stato e i risultati incrementali. Questo assicura che i gestori evento del client vengano chiamati sul thread o contesto corretto per il modello dell'applicazione. Quando `BuildPrimeNumberList` trova un numero primo, lo segnala come risultato incrementale al gestore eventi del client per l'evento `ProgressChanged`. A questo scopo, è necessaria una classe derivata da <xref:System.ComponentModel.ProgressChangedEventArgs>, chiamata `CalculatePrimeProgressChangedEventArgs`, con una proprietà aggiunta chiamata `LatestPrimeNumber`.  
  
     Il metodo `BuildPrimeNumberList` chiama anche periodicamente il metodo `TaskCanceled` ed esce se il metodo restituisce `true`.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#5)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#5)]  
  
4. Implementare `IsPrime`. Il metodo accetta tre parametri: un elenco di numeri primi noti, il numero da testare e un parametro di output per il primo divisore trovato. Dato l'elenco di numeri primi, determina se il numero di test è un numero primo.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#28](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#28)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#28](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#28)]  
  
5. Derivare `CalculatePrimeProgressChangedEventArgs` da <xref:System.ComponentModel.ProgressChangedEventArgs>. Questa classe è necessaria per segnalare i risultati incrementali al gestore eventi del client per l'evento `ProgressChanged`. Contiene una proprietà aggiuntiva denominata `LatestPrimeNumber`.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#29](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#29)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#29](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#29)]  
  
## <a name="checkpoint"></a>Checkpoint  
 A questo punto, è possibile compilare il componente.  
  
### <a name="to-test-your-component"></a>Per eseguire il test del componente  
  
- Compilare il componente.  
  
     Gli unici elementi ancora da scrivere sono i metodi che avviano e annullano le operazioni asincrone, `CalculatePrimeAsync` e `CancelAsync`.  
  
## <a name="implementing-the-start-and-cancel-methods"></a>Implementazione dei metodi di annullamento e di avvio  
 Per avviare il metodo di lavoro nel relativo thread, chiamare `BeginInvoke` sul delegato che ne esegue il wrapping. Per gestire la durata di una determinata operazione asincrona, si chiama il metodo <xref:System.ComponentModel.AsyncOperationManager.CreateOperation%2A> sulla classe helper <xref:System.ComponentModel.AsyncOperationManager>. Viene restituita una classe <xref:System.ComponentModel.AsyncOperation>, che effettua il marshalling delle chiamate sui gestori eventi del client al thread o al contesto appropriato.  
  
 Per annullare una determinata operazione in sospeso, chiamare <xref:System.ComponentModel.AsyncOperation.PostOperationCompleted%2A> sulla classe <xref:System.ComponentModel.AsyncOperation> corrispondente. Verrà terminata l'operazione e tutte le chiamate successive alla classe <xref:System.ComponentModel.AsyncOperation> genereranno un'eccezione.  
  
### <a name="to-implement-start-and-cancel-functionality"></a>Per implementare la funzionalità di avvio e annullamento:  
  
1. Implementare il metodo `CalculatePrimeAsync`. Verificare che il token fornito dal client (ID attività) sia univoco rispetto a tutti i token che rappresentano le attività attualmente in sospeso. Se il client passa un token non univoco, `CalculatePrimeAsync` genera un'eccezione. In caso contrario, il token viene aggiunto alla raccolta di ID attività.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#3)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#3)]  
  
2. Implementare il metodo `CancelAsync`. Se il parametro `taskId` esiste nella raccolta di token, viene rimosso. In questo modo viene impedita l'esecuzione delle attività annullate non avviate. Se l'attività è in esecuzione, il metodo `BuildPrimeNumberList` termina quando rileva che l'ID attività è stato rimosso dalla raccolta della durata.  
  
     [!code-csharp[System.ComponentModel.AsyncOperationManager#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#4)]
     [!code-vb[System.ComponentModel.AsyncOperationManager#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#4)]  
  
## <a name="checkpoint"></a>Checkpoint  
 A questo punto, è possibile compilare il componente.  
  
### <a name="to-test-your-component"></a>Per eseguire il test del componente  
  
- Compilare il componente.  
  
 Il componente `PrimeNumberCalculator` è ora completo e pronto per l'uso.  
  
 Per un client di esempio che usa il componente `PrimeNumberCalculator`, vedere [Procedura: Implementare un client del modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md).  
  
## <a name="next-steps"></a>Passaggi successivi  
 È possibile compilare questo esempio scrivendo `CalculatePrime`, l'equivalente sincrono del metodo `CalculatePrimeAsync`. In questo modo il componente `PrimeNumberCalculator` risulta completamente compatibile con il modello asincrono basato su eventi.  
  
 È possibile migliorare questo esempio conservando l'elenco di tutti i numeri primi individuati dalle varie chiamate per i diversi numeri di test. Usando questo approccio, ogni attività usufruirà del lavoro svolto dalle attività precedenti. Assicurarsi di proteggere l'elenco con aree `lock`, in modo che l'accesso all'elenco da thread diversi venga serializzato.  
  
 È anche possibile migliorare l'esempio testando i divisori semplici, ad esempio 2, 3 e 5.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Eseguire un'operazione in background](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)
- [Cenni preliminari sul modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) (Modello asincrono basato su eventi, EAP)
