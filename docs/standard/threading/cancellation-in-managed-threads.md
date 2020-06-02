---
title: Annullamento in thread gestiti
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cancellation in .NET, overview
ms.assetid: eea11fe5-d8b0-4314-bb5d-8a58166fb1c3
ms.openlocfilehash: e56d0f71afdc9281271b7d15316a133e7c720bd0
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84277882"
---
# <a name="cancellation-in-managed-threads"></a>Annullamento in thread gestiti
A partire da .NET Framework 4, .NET Framework usa un modello unificato per l'annullamento cooperativo di operazioni asincrone o di operazioni sincrone a esecuzione prolungata. Questo modello è basato su un oggetto leggero chiamato token di annullamento. L'oggetto che richiama una o più operazioni annullabili, ad esempio tramite la creazione di nuovi thread o attività, passa il token a ogni operazione. Singole operazioni possono a loro volta passare copie del token ad altre operazioni. In un secondo momento, l'oggetto che ha creato il token può usarlo per richiedere che le operazioni arrestino le rispettive attività. Solo l'oggetto richiedente può inviare la richiesta di annullamento e ogni listener è responsabile del rilevamento della richiesta e della relativa risposta in modo appropriato e tempestivo.  
  
 Il criterio generale per implementare il modello di annullamento cooperativo è il seguente:  
  
- Creare un'istanza di un oggetto <xref:System.Threading.CancellationTokenSource>, che gestisce e invia la notifica di annullamento ai singoli token di annullamento.  
  
- Passare il token restituito dalla proprietà <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=nameWithType> a ogni attività o thread in attesa di annullamento.  
  
- Specificare un meccanismo per ogni attività o thread per rispondere all'annullamento.  
  
- Chiamare il metodo <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=nameWithType> per fornire la notifica di annullamento.  
  
> [!IMPORTANT]
> La classe <xref:System.Threading.CancellationTokenSource> implementa l'interfaccia <xref:System.IDisposable>. Assicurarsi di chiamare il metodo <xref:System.Threading.CancellationTokenSource.Dispose%2A?displayProperty=nameWithType> dopo aver usato l'origine del token di annullamento per liberare qualsiasi risorsa gestita che contiene.  
  
 L'immagine seguente mostra la relazione tra l'origine di un token e tutte le copie del token.  
  
 ![CancellationTokenSource e token di annullamento](media/vs-cancellationtoken.png "VS_CancellationToken")  
  
 Il nuovo modello di annullamento semplifica la creazione di applicazioni e librerie in grado di riconoscere l'annullamento e supporta le funzionalità seguenti:  
  
- L'annullamento è cooperativo e non viene forzato nel listener. Il listener determina come eseguire normalmente la terminazione in risposta a una richiesta di annullamento.  
  
- La richiesta è diversa dall'ascolto. Un oggetto che richiama un'operazione annullabile può controllare il momento (se applicabile) in cui è necessario un annullamento.  
  
- L'oggetto richiedente invia la richiesta di annullamento a tutte le copie del token usando solo una chiamata di metodo.  
  
- Un listener può restare in ascolto di più token simultaneamente unendoli in un *token collegato*.  
  
- Il codice utente può rilevare e rispondere alle richieste di annullamento dal codice di libreria e il codice di libreria può rilevare e rispondere alle richieste di annullamento dal codice utente.  
  
- I listener possono ricevere notifiche delle richieste di annullamento tramite polling, registrazione dei callback o attesa di handle di attesa.  
  
## <a name="cancellation-types"></a>Tipi di annullamento  
 Il framework di annullamento viene implementato come set di tipi correlati, elencati nella tabella seguente.  
  
|Nome tipo|Descrizione|  
|---------------|-----------------|  
|<xref:System.Threading.CancellationTokenSource>|Oggetto che crea un token di annullamento e che invia inoltre la richiesta di annullamento per tutte le copie del token.|  
|<xref:System.Threading.CancellationToken>|Tipo di valore leggero passato a uno o più listener, in genere come parametro di un metodo. I listener monitorano il valore della proprietà `IsCancellationRequested` del token tramite polling, callback o handle di attesa.|  
|<xref:System.OperationCanceledException>|Gli overload del costruttore di questa eccezione accettano un oggetto <xref:System.Threading.CancellationToken> come parametro. I listener possono facoltativamente generare questa eccezione per verificare l'origine dell'annullamento e notificare ad altri che ha risposto a una richiesta di annullamento.|  
  
 Il nuovo modello di annullamento è integrato in .NET Framework in diversi tipi. I più importanti sono <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> e <xref:System.Linq.ParallelEnumerable?displayProperty=nameWithType>. È consigliabile usare questo nuovo modello di annullamento per tutto il nuovo codice di libreria e applicazione.  
  
## <a name="code-example"></a>Esempio di codice  
 Nell'esempio seguente l'oggetto richiedente crea un oggetto <xref:System.Threading.CancellationTokenSource> e quindi ne passa la proprietà <xref:System.Threading.CancellationTokenSource.Token%2A> all'operazione annullabile. L'operazione che riceve la richiesta monitora il valore della proprietà <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> del token tramite polling. Quando il valore diventa `true`, il listener può essere terminato nel modo più appropriato. In questo esempio avviene semplicemente l'uscita del metodo, che nella maggior parte dei casi è tutto ciò che serve.  
  
> [!NOTE]
> L'esempio usa il metodo <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> per dimostrare che il nuovo framework di annullamento è compatibile con le API legacy. Per un esempio che usi il nuovo tipo <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> preferito, vedere [Procedura: Annullare un'attività e i relativi figli](../parallel-programming/how-to-cancel-a-task-and-its-children.md).  
  
 [!code-csharp[Cancellation#1](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex1.cs#1)]
 [!code-vb[Cancellation#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex1.vb#1)]  
  
## <a name="operation-cancellation-versus-object-cancellation"></a>Confronto tra l'annullamento di operazioni e l'annullamento di oggetti  
 Nel nuovo framework di annullamento l'annullamento è riferito alle operazioni e non agli oggetti. La richiesta di annullamento significa che l'operazione deve essere arrestata il prima possibile dopo l'esecuzione della pulizia necessaria. Un token di annullamento deve fare riferimento a una "operazione annullabile", ma tale operazione può essere implementata nel programma. Se la proprietà <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> del token viene impostata su `true`, non può più essere reimpostata su `false`. Di conseguenza, i token di annullamento non possono essere riutilizzati una volta annullati.  
  
 Se è necessario un meccanismo di annullamento di oggetti, è possibile basarlo sul meccanismo di annullamento di operazioni chiamando il metodo <xref:System.Threading.CancellationToken.Register%2A?displayProperty=nameWithType>, come mostrato nell'esempio seguente.  
  
 [!code-csharp[Cancellation#2](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/objectcancellation1.cs#2)]
 [!code-vb[Cancellation#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/objectcancellation1.vb#2)]  
  
 Se un oggetto supporta più operazioni annullabili simultanee, passare un token separato come input a ogni operazione annullabile diversa. In questo modo, è possibile annullare un'operazione senza influire sulle altre.  
  
## <a name="listening-and-responding-to-cancellation-requests"></a>Ascolto e risposta alle richieste di annullamento  
 Nel delegato dell'utente l'implementatore di un'operazione annullabile determina il modo in cui terminare l'operazione in risposta a una richiesta di annullamento. In molti casi, il delegato dell'utente può eseguire solo la pulizia necessaria e quindi riprendere immediatamente.  
  
 Tuttavia, in casi più complessi il delegato dell'utente potrebbe dover notificare al codice di libreria il verificarsi dell'annullamento. In questi casi, il modo corretto di terminare l'operazione per il delegato consiste nel chiamare il metodo <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>, che provoca la generazione di un'eccezione <xref:System.OperationCanceledException>. Il codice di libreria può rilevare l'eccezione nel thread del delegato dell'utente ed esaminare il token dell'eccezione per determinare se l'eccezione indica l'annullamento cooperativo o un'altra situazione eccezionale.  
  
 La classe <xref:System.Threading.Tasks.Task> gestisce <xref:System.OperationCanceledException> in questo modo. Per altre informazioni, vedere [Task Cancellation](../parallel-programming/task-cancellation.md).  
  
### <a name="listening-by-polling"></a>Ascolto tramite polling  
 Per calcoli a esecuzione prolungata che eseguono cicli o sono ricorsivi, è possibile restare in ascolto di una richiesta di annullamento eseguendo periodicamente il polling del valore della proprietà <xref:System.Threading.CancellationToken.IsCancellationRequested%2A?displayProperty=nameWithType>. Se il valore della proprietà è `true`, il metodo deve eseguire la pulizia e quindi deve essere terminato il più rapidamente possibile. La frequenza di polling ottimale dipende dal tipo di applicazione. È compito dello sviluppatore determinare la migliore frequenza di polling per qualsiasi programma specifico. Il polling in sé non ha un impatto significativo sulle prestazioni. L'esempio seguente mostra uno dei modi in cui è possibile eseguire il polling.  
  
 [!code-csharp[Cancellation#3](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex11.cs#3)]
 [!code-vb[Cancellation#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex11.vb#3)]  
  
 Per un esempio più completo, vedere [Procedura: Mettersi in ascolto di richieste di annullamento tramite polling](how-to-listen-for-cancellation-requests-by-polling.md).  
  
### <a name="listening-by-registering-a-callback"></a>Ascolto tramite registrazione di un callback  
 Alcune operazioni possono venire bloccate in modo da non poter controllare il valore del token di annullamento in modo tempestivo. In questi casi, è possibile registrare un metodo di callback che sblocca il metodo quando viene ricevuta una richiesta di annullamento.  
  
 Il metodo <xref:System.Threading.CancellationToken.Register%2A> restituisce un oggetto <xref:System.Threading.CancellationTokenRegistration> che viene usato per questo scopo specifico. L'esempio seguente mostra come usare il metodo <xref:System.Threading.CancellationToken.Register%2A> per annullare una richiesta Web asincrona.  
  
 [!code-csharp[Cancellation#4](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex4.cs#4)]
 [!code-vb[Cancellation#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex4.vb#4)]  
  
 L'oggetto <xref:System.Threading.CancellationTokenRegistration> gestisce la sincronizzazione dei thread e garantisce l'arresto dell'esecuzione del callback in un momento preciso.  
  
 Per garantire velocità di risposta del sistema ed evitare deadlock, è necessario seguire le linee guida indicate di seguito per la registrazione dei callback:  
  
- Il metodo di callback deve essere rapido perché viene chiamato in modo sincrono e di conseguenza la chiamata a <xref:System.Threading.CancellationTokenSource.Cancel%2A> non viene restituita fino alla restituzione del callback.  
  
- Se si chiama <xref:System.Threading.CancellationTokenRegistration.Dispose%2A> durante l'esecuzione del callback e si mantiene un blocco di cui il callback è in attesa, il programma può subire un deadlock. Quando viene restituito `Dispose`, è possibile liberare qualsiasi risorsa necessaria per il callback.  
  
- I callback non devono eseguire alcun thread manuale o utilizzo di <xref:System.Threading.SynchronizationContext> in un callback. Se un callback deve essere eseguito in un determinato thread, usare il costruttore <xref:System.Threading.CancellationTokenRegistration?displayProperty=nameWithType>, che permette di specificare che l'oggetto syncContext di destinazione è l'oggetto <xref:System.Threading.SynchronizationContext.Current%2A?displayProperty=nameWithType> attivo. L'esecuzione manuale di threading in un callback può provocare un deadlock.  
  
 Per un esempio più completo, vedere [Procedura: Registrare i callback per le richieste di annullamento](how-to-register-callbacks-for-cancellation-requests.md).  
  
### <a name="listening-by-using-a-wait-handle"></a>Ascolto tramite un handle di attesa  
 Quando un'operazione annullabile può restare bloccata mentre è in attesa di una primitiva di sincronizzazione come <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> o <xref:System.Threading.Semaphore?displayProperty=nameWithType>, è possibile usare la proprietà <xref:System.Threading.CancellationToken.WaitHandle%2A?displayProperty=nameWithType> per permettere all'operazione di attendere sia l'evento sia la richiesta di annullamento. L'handle di attesa del token di annullamento verrà segnalato in risposta a una richiesta di annullamento e il metodo può usare il valore restituito del metodo <xref:System.Threading.WaitHandle.WaitAny%2A> per determinare se la segnalazione è stata eseguita dal token di annullamento. L'operazione può quindi semplicemente uscire oppure generare un'eccezione <xref:System.OperationCanceledException>, a seconda del comportamento più appropriato.  
  
 [!code-csharp[Cancellation#5](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex9.cs#5)]
 [!code-vb[Cancellation#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex9.vb#5)]  
  
 Nel nuovo codice destinato a .NET Framework 4, <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> e <xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType> supportano entrambi il nuovo framework di annullamento nei rispettivi metodi `Wait`. È possibile passare <xref:System.Threading.CancellationToken> al metodo e quando viene richiesto l'annullamento, l'evento viene attivato e genera un'eccezione <xref:System.OperationCanceledException>.  
  
 [!code-csharp[Cancellation#6](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex10.cs#6)]
 [!code-vb[Cancellation#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex10.vb#6)]  
  
 Per un esempio più completo, vedere [Procedura: Mettersi in ascolto di richieste di annullamento con handle di attesa](how-to-listen-for-cancellation-requests-that-have-wait-handles.md).  
  
### <a name="listening-to-multiple-tokens-simultaneously"></a>Ascolto di più token simultaneamente  
 In alcuni casi, un listener può dover essere in ascolto di più token di annullamento simultaneamente. Ad esempio, un'operazione di annullamento può dover monitorare un token di annullamento interno oltre a un token passato esternamente come argomento al parametro di un metodo. A questo scopo, creare l'origine di un token collegato in grado di unire due o più token in uno solo, come mostrato nell'esempio seguente.  
  
 [!code-csharp[Cancellation#7](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex13.cs#7)]
 [!code-vb[Cancellation#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex13.vb#7)]  
  
 Notare che è necessario chiamare `Dispose` nell'origine del token collegato al suo completamento. Per un esempio più completo, vedere [Procedura: Ascolto di più richieste di annullamento](how-to-listen-for-multiple-cancellation-requests.md).  
  
## <a name="cooperation-between-library-code-and-user-code"></a>Cooperazione tra codice di libreria e codice utente  
 Il framework di annullamento unificato permette al codice di libreria di annullare il codice utente e al codice utente di annullare il codice libreria in modo cooperativo. Una cooperazione uniforme dipende da ognuno dei due lati in base alle linee guida seguenti:  
  
- Se il codice di libreria fornisce operazioni annullabili, deve anche fornire metodi pubblici che accettano un token di annullamento esterno, in modo che il codice utente possa richiedere l'annullamento.  
  
- Se il codice di libreria esegue chiamate nel codice utente, deve interpretare un oggetto OperationCanceledException(externalToken) come *annullamento cooperativo* e non necessariamente come eccezione di errore.  
  
- I delegati dell'utente devono tentare di rispondere alle richieste di annullamento dal codice di libreria in modo tempestivo.  
  
 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> e <xref:System.Linq.ParallelEnumerable?displayProperty=nameWithType> sono esempi di classi che seguono queste linee guida. Per altre informazioni, vedere [annullamento delle attività](../parallel-programming/task-cancellation.md) e [procedura: annullare una query PLINQ](../parallel-programming/how-to-cancel-a-plinq-query.md).  
  
## <a name="see-also"></a>Vedere anche

- [Nozioni fondamentali sul threading gestito](managed-threading-basics.md)
