---
title: Modello asincrono basato su attività (TAP)
description: Informazioni sul modello asincrono basato su attività (TAP). TAP è il modello di progettazione asincrono consigliato per lo sviluppo in .NET.
ms.date: 02/26/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- .NET Framework, and TAP
- asynchronous design patterns, .NET Framework
- TAP, .NET Framework support for
- Task-based Asynchronous Pattern, .NET Framework support for
- .NET Framework, asynchronous design patterns
ms.assetid: 8cef1fcf-6f9f-417c-b21f-3fd8bac75007
ms.openlocfilehash: 36784cd403891ddbeb4ea6d22ad89640ce1234c3
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768495"
---
# <a name="task-based-asynchronous-pattern-tap"></a>Modello asincrono basato su attività (TAP)
Il modello asincrono basato su attività (TAP) è basato sui tipi <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> nello spazio dei nomi <xref:System.Threading.Tasks?displayProperty=nameWithType>, che vengono usati per rappresentare le operazioni asincrone arbitrarie. TAP è il modello di progettazione asincrono consigliato per le nuove attività di sviluppo.  
  
## <a name="naming-parameters-and-return-types"></a>Denominazione, parametri e tipi restituiti

TAP usa un singolo metodo per rappresentare l'inizio e il completamento di un'operazione asincrona. Tale comportamento è in contrasto sia con il modello di programmazione asincrona (APM o `IAsyncResult`) che con il modello asincrono basato su eventi (EAP). Il modello di programmazione asincrona richiede i metodi `Begin` ed `End`. Il modello asincrono basato su eventi richiede un metodo con il suffisso `Async`, oltre a uno o più eventi, i tipi delegati del gestore eventi e i tipi derivati da `EventArg`. I metodi asincroni in TAP includono il suffisso `Async` dopo il nome dell'operazione per i metodi che restituiscono tipi awaitable, ad esempio, <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.ValueTask> e <xref:System.Threading.Tasks.ValueTask%601>. Ad esempio, un'operazione `Get` asincrona che restituisce `Task<String>` può essere denominata `GetAsync`. Se si aggiunge un metodo TAP a una classe che contiene già il nome di un metodo EAP con il suffisso `Async`, usare invece il suffisso `TaskAsync`. Ad esempio, se la classe dispone già di un metodo `GetAsync`, usare il nome `GetTaskAsync`. Se un metodo avvia un'operazione asincrona, ma non restituisce un tipo awaitable, il nome dovrebbe iniziare con `Begin`, `Start` o un altro verbo per suggerire che questo metodo non restituisce o genera il risultato dell'operazione.  
  
 Un metodo TAP restituisce <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> o <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>, a seconda che il metodo sincrono corrispondente restituisca void o un tipo `TResult`.  
  
 I parametri di un metodo TAP devono corrispondere ai parametri della relativa controparte sincrona e devono essere forniti nello stesso ordine.  Tuttavia, i parametri `out` e `ref` sono esclusi da questa regola e dovrebbero essere evitati completamente. Tutti i dati che dovrebbero venire restituiti da un parametro `out` o `ref` dovranno invece essere restituiti come parte di `TResult` restituito da <xref:System.Threading.Tasks.Task%601> e usare una tupla o una struttura dei dati personalizzata per contenere più valori. È anche consigliabile valutare l'opportunità di aggiungere un parametro <xref:System.Threading.CancellationToken> anche se la controparte sincrona del metodo TAP non ne offre uno.

 I metodi dedicati esclusivamente alla creazione, modifica o combinazione di attività (dove l'intento asincrono del metodo risulta chiaro nel nome del metodo o nel nome del tipo a cui appartiene il metodo) non devono seguire questo modello di denominazione. Tali metodi vengono spesso definiti *combinatori*. Esempi di combinatori includono <xref:System.Threading.Tasks.Task.WhenAll%2A> e <xref:System.Threading.Tasks.Task.WhenAny%2A> e sono illustrati nella sezione [Utilizzo di combinatori incorporati basati su attività](consuming-the-task-based-asynchronous-pattern.md#combinators) dell'articolo [Utilizzo del modello asincrono basato su attività](consuming-the-task-based-asynchronous-pattern.md).  
  
 Per esempi relativi alle differenze di sintassi di TAP rispetto ai modelli di programmazione asincrona legacy, come il modello di programmazione asincrono (APM) e il modello asincrono basato su eventi (EAP), vedere [Modelli di programmazione asincrona](index.md).  
  
## <a name="initiating-an-asynchronous-operation"></a>Avvio di un'operazione asincrona  
 Un metodo asincrono basato su TAP può eseguire una piccola quantità di lavoro in modo sincrono, ad esempio convalidare gli argomenti e avviare l'operazione asincrona, prima di restituire l'attività risultante. Le attività sincrone devono essere minime in modo che il metodo asincrono possa eseguire rapidamente la restituzione. I motivi per una restituzione rapida includono:  
  
- I metodi asincroni possono essere richiamati dai thread dell'interfaccia utente e le attività sincrone a esecuzione prolungata potrebbero compromettere la velocità di risposta dell'applicazione.  
  
- Più metodi asincroni possono essere avviati simultaneamente. Pertanto, le attività a esecuzione prolungata nella parte sincrona di un metodo asincrono possono ritardare l'avvio di altre operazioni asincrone, riducendo quindi i vantaggi della concorrenza.  
  
 In alcuni casi, la quantità di lavoro richiesta per completare l'operazione è inferiore alla quantità di lavoro richiesta per avviare un'operazione in modo asincrono. La lettura da un flusso in cui l'operazione di lettura può essere soddisfatta dai dati che sono già stati memorizzati nel buffer in memoria è un esempio di tale scenario. In tali casi, l'operazione può essere completata in modo sincrono e può restituire un'attività già completata.  
  
## <a name="exceptions"></a>Eccezioni  
 Un metodo asincrono dovrebbe generare un'eccezione utilizzabile da una chiamata al metodo asincrono solo in risposta a un errore di utilizzo. Gli errori di utilizzo non devono mai verificarsi nel codice di produzione. Ad esempio, se passando un riferimento Null (`Nothing` in Visual Basic) come uno degli argomenti del metodo si determina uno stato di errore (generalmente rappresentato da un'eccezione <xref:System.ArgumentNullException>), è possibile modificare il codice chiamante per assicurarsi che un riferimento Null non venga mai passato. Per tutti gli altri errori, le eccezioni che si verificano quando un metodo asincrono è in esecuzione devono essere assegnate all'attività restituita, anche se il metodo asincrono viene completato in modo sincrono prima che l'attività venga restituita. In genere, un'attività contiene al massimo un'eccezione. Tuttavia, se l'attività rappresenta più operazioni, (ad esempio <xref:System.Threading.Tasks.Task.WhenAll%2A>), più eccezioni possono essere associate a una singola attività.  
  
## <a name="target-environment"></a>Ambiente di destinazione  
 Quando si implementa un metodo TAP, è possibile determinare quando si verifica l'esecuzione asincrona. È possibile scegliere di eseguire il carico di lavoro nel pool di thread, implementarlo mediante I/O asincrono (senza associazione a un thread per la maggior parte dell'esecuzione delle operazioni), eseguirlo in un thread specifico (come il thread UI) o usare il numero desiderato di contesti potenziali. Un metodo TAP può anche non avere alcun elemento da eseguire e restituire solo un <xref:System.Threading.Tasks.Task> che rappresenta l'occorrenza di una condizione in un'altra posizione nel sistema (ad esempio, un'attività che rappresenta i dati provenienti da una struttura di dati in coda).

 Il chiamante del metodo TAP può smettere di attendere il completamento del metodo TAP rimanendo in attesa in modalità sincrona dell'attività risultante o potrebbe eseguire codice aggiuntivo (continuazione) al completamento dell'operazione asincrona. L'autore del codice di continuazione è in grado di controllare dove viene eseguito il codice. È possibile creare il codice di continuazione in modo esplicito, con i metodi della classe <xref:System.Threading.Tasks.Task>, (ad esempio <xref:System.Threading.Tasks.Task.ContinueWith%2A>), o in modo implicito, usando il supporto linguistico compilato sulla base delle continuazioni, (ad esempio `await` in C#, `Await` in Visual Basic, `AwaitValue` in F#).  
  
## <a name="task-status"></a>Stato dell'attività  
 La classe <xref:System.Threading.Tasks.Task> fornisce un ciclo di vita per le operazioni asincrone e il ciclo è rappresentato dall'enumerazione <xref:System.Threading.Tasks.TaskStatus>. Per supportare i casi estremi di tipi che derivano da <xref:System.Threading.Tasks.Task> e da <xref:System.Threading.Tasks.Task%601> e per supportare la separazione della costruzione dalla pianificazione, la classe <xref:System.Threading.Tasks.Task> espone un metodo <xref:System.Threading.Tasks.Task.Start%2A>. Le attività create dai costruttori <xref:System.Threading.Tasks.Task> pubblici vengono definite *attività inattive*, poiché iniziano il ciclo di vita nello stato non pianificato <xref:System.Threading.Tasks.TaskStatus.Created> e vengono pianificate solo quando <xref:System.Threading.Tasks.Task.Start%2A> viene chiamato su queste istanze.

 Tutte le altre attività iniziano il ciclo di vita in uno stato attivo, ovvero le operazioni asincrone che rappresentano sono già state avviate e lo stato dell'attività è un valore di enumerazione diverso da <xref:System.Threading.Tasks.TaskStatus.Created?displayProperty=nameWithType>. Tutte le attività che vengono restituite dai metodi TAP devono essere attivate. **Se un metodo TAP usa internamente il costruttore di un'attività per creare un'istanza dell'attività da restituire, tale metodo deve chiamare <xref:System.Threading.Tasks.Task.Start%2A> sull'oggetto <xref:System.Threading.Tasks.Task> prima della restituzione.** I consumer di un metodo TAP possono presumere in modo sicuro che l'attività restituita sia attiva e non devono tentare di chiamare <xref:System.Threading.Tasks.Task.Start%2A> su alcun oggetto <xref:System.Threading.Tasks.Task> restituito da un metodo TAP. Se si chiama <xref:System.Threading.Tasks.Task.Start%2A> su un'attività attiva, viene generata un'eccezione <xref:System.InvalidOperationException>.  
  
## <a name="cancellation-optional"></a>Annullamento (facoltativo)  
 In TAP, l'annullamento è facoltativo sia per gli implementatori di metodi asincroni che i consumer di metodi asincroni. Se un'operazione consente l'annullamento, espone un overload del metodo asincrono che accetta un token di annullamento (istanza di<xref:System.Threading.CancellationToken>). Convenzionalmente, al parametro viene assegnato il nome `cancellationToken`.  
  
 [!code-csharp[Conceptual.TAP#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap/cs/examples1.cs#1)]
 [!code-vb[Conceptual.TAP#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap/vb/examples1.vb#1)]  
  
 L'operazione asincrona esamina questo token per le richieste di annullamento. Se riceve una richiesta di annullamento, può scegliere di soddisfarla e annullare l'operazione. Se la richiesta di annullamento determina la fine anticipata del lavoro, il metodo TAP restituisce un'attività che termina nello stato <xref:System.Threading.Tasks.TaskStatus.Canceled>; non esiste alcun risultato disponibile e non viene generata alcuna eccezione.  Lo stato <xref:System.Threading.Tasks.TaskStatus.Canceled> è considerato uno stato finale (o completato) per un task, insieme a <xref:System.Threading.Tasks.TaskStatus.Faulted> e <xref:System.Threading.Tasks.TaskStatus.RanToCompletion>. Pertanto, se un'attività è nello stato <xref:System.Threading.Tasks.TaskStatus.Canceled>, la proprietà <xref:System.Threading.Tasks.Task.IsCompleted%2A> restituisce `true`. Quando un'attività viene completata nello stato <xref:System.Threading.Tasks.TaskStatus.Canceled>, tutte le continuazioni registrate con l'attività vengono pianificate o eseguite, a meno che sia stata specificata un'opzione di continuazione come <xref:System.Threading.Tasks.TaskContinuationOptions.NotOnCanceled> per escludere la continuazione. Qualsiasi codice in attesa in modo asincrono di un'attività annullata tramite l'utilizzo di funzionalità del linguaggio continua a essere eseguito ma riceve <xref:System.OperationCanceledException> o un'eccezione derivata. Il codice bloccato in attesa in modo sincrono dell'attività tramite metodi come <xref:System.Threading.Tasks.Task.Wait%2A> e <xref:System.Threading.Tasks.Task.WaitAll%2A> continua anch'esso ad essere eseguito con un'eccezione.  
  
 Se un token di annullamento ha richiesto l'annullamento prima che venga chiamato il metodo TAP che accetta il token, il metodo TAP deve restituire un'attività <xref:System.Threading.Tasks.TaskStatus.Canceled>.  Tuttavia, se viene richiesto l'annullamento mentre l'operazione asincrona è in esecuzione, tale operazione non ha bisogno di accettare la richiesta di annullamento.  L'attività restituita deve terminare nello stato <xref:System.Threading.Tasks.TaskStatus.Canceled> solo se l'operazione termina come risultato della richiesta di annullamento. Se viene richiesto l'annullamento ma viene comunque prodotto un risultato o un'eccezione, l'attività deve terminare nello stato <xref:System.Threading.Tasks.TaskStatus.RanToCompletion> o <xref:System.Threading.Tasks.TaskStatus.Faulted>.

 Per i metodi asincroni per i quali si vuole esporre la possibilità di annullarli, non si deve specificare un overload che non accetta un token di annullamento. Per i metodi che non possono essere annullati, non fornire gli overload che accettano un token di annullamento; ciò indica al chiamante se il metodo di destinazione è realmente annullabile.  Il codice del consumer che non richiede l'annullamento può chiamare un metodo che accetta <xref:System.Threading.CancellationToken> e fornisce <xref:System.Threading.CancellationToken.None%2A> come valore dell'argomento. <xref:System.Threading.CancellationToken.None%2A> è equivalente dal punto di vista funzionale all'oggetto predefinito <xref:System.Threading.CancellationToken>.  
  
## <a name="progress-reporting-optional"></a>Creazione di report sullo stato di avanzamento (facoltativo)  
 Alcune operazioni asincrone prevedono il vantaggio dell'invio di notifiche sullo stato di avanzamento; queste vengono in genere usate per aggiornare un'interfaccia utente con informazioni sullo stato di avanzamento dell'operazione asincrona.

 In TAP, lo stato di avanzamento viene gestito mediante un'interfaccia <xref:System.IProgress%601>, che viene passata al metodo asincrono come un parametro in genere denominato `progress`.  La fornitura dell'interfaccia dello stato di avanzamento quando viene chiamato il metodo asincrono consente di eliminare le race condition che derivano da un utilizzo non corretto (ovvero quando gestori eventi non registrati correttamente dopo l'inizio delle operazioni possono non rilevare gli aggiornamenti).  Ancora più importante, l'interfaccia dello stato di avanzamento supporta varie implementazioni dello stato di avanzamento, in base a quanto determinato dal codice consumer.  Ad esempio, il codice consumer potrebbe controllare solo l'ultimo aggiornamento dello stato di avanzamento o memorizzare nel buffer tutti gli aggiornamenti o ancora richiamare un'azione per ogni aggiornamento oppure verificare che venga eseguito il marshalling della chiamata a un particolare thread. Tutte queste opzioni possono essere realizzate tramite un'implementazione diversa dell'interfaccia, personalizzata in base ai specifici requisiti del consumer.  Come per l'annullamento, le implementazioni TAP devono fornire un parametro <xref:System.IProgress%601> solo se l'API supporta le notifiche dello stato di avanzamento.

 Ad esempio, se il metodo `ReadAsync` illustrato in precedenza in questo articolo può segnalare lo stato di avanzamento intermedio sotto forma di numero di byte letti fino a qual momento, il callback dello stato di avanzamento può essere un'interfaccia <xref:System.IProgress%601>:  
  
 [!code-csharp[Conceptual.TAP#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap/cs/examples1.cs#2)]
 [!code-vb[Conceptual.TAP#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap/vb/examples1.vb#2)]  
  
 Se un metodo `FindFilesAsync` restituisce un elenco di tutti i file che soddisfano un criterio di ricerca particolare, il callback dello stato di avanzamento può fornire una stima della percentuale di lavoro completato e il set corrente di risultati parziali.  A tale scopo è possibile usare una tupla:  
  
 [!code-csharp[Conceptual.TAP#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap/cs/examples1.cs#3)]
 [!code-vb[Conceptual.TAP#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap/vb/examples1.vb#3)]  
  
 Oppure un tipo di dati specifico dell'API:  
  
 [!code-csharp[Conceptual.TAP#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.tap/cs/examples1.cs#4)]
 [!code-vb[Conceptual.TAP#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.tap/vb/examples1.vb#4)]  
  
 Nel secondo caso, il tipo di dati speciale in genere presenta il suffisso `ProgressInfo`.  
  
 Se le implementazioni TAP forniscono overload che accettano un parametro `progress`, devono consentire che l'argomento sia `null`, nel qual caso non verrà segnalato alcuno stato di avanzamento. Le implementazioni TAP devono segnalare lo stato di avanzamento all'oggetto <xref:System.Progress%601> in modo sincrono, in modo che il metodo asincrono possa fornire rapidamente lo stato di avanzamento e il consumer dello stato di avanzamento possa determinare il miglior modo per gestire le informazioni. Ad esempio, l'istanza dello stato di avanzamento può scegliere di effettuare il marshalling dei callback e generare eventi in un contesto di sincronizzazione acquisito.  
  
## <a name="iprogresst-implementations"></a>\<T>Implementazioni IProgress  
 .NET Framework 4.5 offre un'unica implementazione di <xref:System.IProgress%601>: <xref:System.Progress%601>. La classe <xref:System.Progress%601> viene dichiarata nel modo seguente:  
  
```csharp  
public class Progress<T> : IProgress<T>  
{  
    public Progress();  
    public Progress(Action<T> handler);  
    protected virtual void OnReport(T value);  
    public event EventHandler<T> ProgressChanged;  
}  
```  
  
```vb  
Public Class Progress(Of T) : Inherits IProgress(Of T)  
    Public Sub New()  
    Public Sub New(handler As Action(Of T))  
    Protected Overridable Sub OnReport(value As T)  
    Public Event ProgressChanged As EventHandler(Of T>  
End Class  
```  
  
 Un'istanza di <xref:System.Progress%601> espone un evento <xref:System.Progress%601.ProgressChanged>, che viene generato ogni volta che l'operazione asincrona segnala un aggiornamento di stato. L'evento <xref:System.Progress%601.ProgressChanged> viene generato sull'oggetto <xref:System.Threading.SynchronizationContext> acquisito quando è stata creata l'istanza di <xref:System.Progress%601>. Se non è disponibile alcun contesto di sincronizzazione, viene usato un contesto predefinito destinato al pool di thread. Gestori possono essere registrati con questo evento. Un singolo gestore può inoltre essere fornito al costruttore <xref:System.Progress%601> per praticità, comportandosi esattamente come un gestore per l'evento <xref:System.Progress%601.ProgressChanged>. Gli aggiornamenti dello stato di avanzamento vengono generati in modo asincrono per evitare di ritardare l'operazione asincrona mentre sono in esecuzione i gestori eventi. Un'altra implementazione <xref:System.IProgress%601> può scegliere di applicare semantiche differenti.  
  
## <a name="choosing-the-overloads-to-provide"></a>Scelta degli overload da fornire  
 Se un'implementazione TAP usa i parametri facoltativi <xref:System.Threading.Tasks.TaskFactory.CancellationToken%2A> e <xref:System.IProgress%601>, potrebbe richiedere fino a quattro overload:  
  
```csharp  
public Task MethodNameAsync(…);  
public Task MethodNameAsync(…, CancellationToken cancellationToken);  
public Task MethodNameAsync(…, IProgress<T> progress);
public Task MethodNameAsync(…,
    CancellationToken cancellationToken, IProgress<T> progress);  
```  
  
```vb  
Public MethodNameAsync(…) As Task  
Public MethodNameAsync(…, cancellationToken As CancellationToken cancellationToken) As Task  
Public MethodNameAsync(…, progress As IProgress(Of T)) As Task
Public MethodNameAsync(…, cancellationToken As CancellationToken,
                       progress As IProgress(Of T)) As Task  
```  
  
 Tuttavia, molte implementazioni TAP non offrono funzionalità né di annullamento né di segnalazione dello stato di avanzamento, pertanto richiedono un singolo metodo:  
  
```csharp  
public Task MethodNameAsync(…);  
```  
  
```vb  
Public MethodNameAsync(…) As Task  
```  
  
 Se l'implementazione TAP supporta l'annullamento o lo stato di avanzamento ma non entrambi, può fornire due overload:  
  
```csharp  
public Task MethodNameAsync(…);  
public Task MethodNameAsync(…, CancellationToken cancellationToken);  
  
// … or …  
  
public Task MethodNameAsync(…);  
public Task MethodNameAsync(…, IProgress<T> progress);  
```  
  
```vb  
Public MethodNameAsync(…) As Task  
Public MethodNameAsync(…, cancellationToken As CancellationToken) As Task  
  
' … or …  
  
Public MethodNameAsync(…) As Task  
Public MethodNameAsync(…, progress As IProgress(Of T)) As Task  
```  
  
 Se l'implementazione TAP supporta sia l'annullamento che lo stato di avanzamento, può esporre tutti e quattro gli overload. Tuttavia, può fornire solo i seguenti due:  
  
```csharp  
public Task MethodNameAsync(…);  
public Task MethodNameAsync(…,
    CancellationToken cancellationToken, IProgress<T> progress);  
```  
  
```vb  
Public MethodNameAsync(…) As Task  
Public MethodNameAsync(…, cancellationToken As CancellationToken,
                       progress As IProgress(Of T)) As Task  
```  
  
 Per compensare le due combinazioni intermedie mancanti, gli sviluppatori possono passare <xref:System.Threading.CancellationToken.None%2A> o un oggetto <xref:System.Threading.CancellationToken> predefinito per il parametro `cancellationToken` e `null` per il parametro `progress`.  
  
 Se si prevede che ogni utilizzo del metodo TAP supporti l'annullamento o lo stato di avanzamento, è possibile omettere gli overload che non accettano il parametro pertinente.  
  
 Se si decide di esporre più overload per rendere facoltativi l'annullamento o lo stato di avanzamento, gli overload che non supportano l'annullamento o lo stato di avanzamento devono comportarsi come se passassero <xref:System.Threading.CancellationToken.None%2A> per l'annullamento o `null` per lo stato di avanzamento all'overload che li supporta.  
  
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Descrizione|  
|-----------|-----------------|  
|[Modelli di programmazione asincrona](index.md)|Vengono illustrati i tre modelli per eseguire le operazioni asincrone: il modello asincrono basato su attività (TAP), il modello di programmazione asincrono (APM) e il modello asincrono basato su eventi (EAP).|  
|[Implementazione del modello asincrono basato su attività](implementing-the-task-based-asynchronous-pattern.md)|Vengono descritti i tre modi per implementare il modello asincrono basato su attività (TAP): tramite i compilatori C# e Visual Basic in Visual Studio, manualmente oppure mediante una combinazione dei primi due.|  
|[Consuming the Task-based Asynchronous Pattern](consuming-the-task-based-asynchronous-pattern.md)|Viene descritto come usare le attività e i callback per ottenere l'attesa senza blocchi.|  
|[Interoperabilità con altri tipi e modelli asincroni](interop-with-other-asynchronous-patterns-and-types.md)|Viene descritto come usare il modello asincrono basato su attività (TAP) per implementare il modello di programmazione asincrono (APM) e il modello asincrono basato su eventi (EAP).|
