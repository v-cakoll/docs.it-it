---
title: Programmazione asincrona con Async e Await
ms.date: 07/20/2015
ms.assetid: bd7e462b-583b-4395-9c36-45aa9e61072c
ms.openlocfilehash: b3ca0398936d257612b30828e3048797894ccc20
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163631"
---
# <a name="asynchronous-programming-with-async-and-await-visual-basic"></a>Programmazione asincrona con Async e await (Visual Basic)

È possibile evitare colli di bottiglia nelle prestazioni e migliorare la risposta generale dell'applicazione utilizzando la programmazione asincrona. Le tecniche tradizionali per la scrittura di applicazioni asincrone, tuttavia, possono essere complesse, rendendone difficile la scrittura, il debug e la gestione.

Visual Studio 2012 introduce un approccio semplificato, la programmazione asincrona, che sfrutta il supporto asincrono in .NET Framework 4.5 e versioni successive oltre che in Windows Runtime. Il compilatore esegue il lavoro difficile che prima veniva svolto dallo sviluppatore e l'applicazione mantiene una struttura logica simile al codice sincrono. Di conseguenza, si ottengono tutti i vantaggi della programmazione asincrona con meno lavoro richiesto.

In questo argomento viene fornita una panoramica di come e quando utilizzare la programmazione asincrona e vengono forniti collegamenti per supportare gli argomenti contenenti informazioni dettagliate ed esempi.

## <a name="BKMK_WhentoUseAsynchrony"></a> Async migliora la velocità di risposta

La modalità asincrona è essenziale per le attività che potenzialmente bloccano l'esecuzione, ad esempio quando l'applicazione accede al Web. L'accesso a una risorsa Web può essere talvolta lento o ritardato. Se tale attività viene bloccata in un processo sincrono, l'intera applicazione deve attendere. In un processo asincrono l'applicazione può invece continuare con un altro lavoro che non dipende dalla risorsa Web finché l'attività di blocco non termina.

Nella tabella seguente sono mostrate le aree tipiche in cui la programmazione asincrona migliora la risposta. Le API elencate da .NET Framework 4.5 e Windows Runtime contengono metodi che supportano la programmazione asincrona.

|Area di applicazione|API di supporto che contengono metodi asincroni|
|----------------------|------------------------------------------------|
|Accesso Web|<xref:System.Net.Http.HttpClient>, <xref:Windows.Web.Syndication.SyndicationClient>|
|Utilizzo dei file|<xref:Windows.Storage.StorageFile>, <xref:System.IO.StreamWriter>, <xref:System.IO.StreamReader>, <xref:System.Xml.XmlReader>|
|Utilizzo delle immagini|<xref:Windows.Media.Capture.MediaCapture>, <xref:Windows.Graphics.Imaging.BitmapEncoder>, <xref:Windows.Graphics.Imaging.BitmapDecoder>|
|Programmazione WCF|[Operazioni sincrone e asincrone](../../../../framework/wcf/synchronous-and-asynchronous-operations.md)|
|||

La modalità asincrona è particolarmente importante per le applicazioni che accedono al thread dell'interfaccia utente poiché tutte le attività correlate all'interfaccia utente in genere condividono un thread. Se un processo è bloccato in un'applicazione sincrona, tutte le attività saranno bloccate. L'applicazione non risponde e si potrebbe pensare che si sia verificato un errore mentre si tratta solo di un'applicazione attesa.

Quando si utilizzano i metodi asincroni, l'applicazione continua a rispondere all'interfaccia utente. È possibile ad esempio ridimensionare o ridurre a icona una finestra oppure è possibile chiudere l'applicazione se non si desidera attendere il completamento.

L'approccio basato su modalità asincrona aggiunge l'equivalente di una trasmissione automatica all'elenco di opzioni da cui è possibile scegliere quando si progettano operazioni asincrone. In questo modo si ottengono tutti i vantaggi della programmazione asincrona tradizionale con meno lavoro richiesto allo sviluppatore.

## <a name="BKMK_HowtoWriteanAsyncMethod"></a> I metodi asincroni sono più semplici da scrivere

In Visual Basic le parole chiave [Async](../../../../visual-basic/language-reference/modifiers/async.md) e [Await](../../../../visual-basic/language-reference/operators/await-operator.md) sono il punto centrale della programmazione asincrona. Tramite queste due parole chiave, è possibile usare le risorse di .NET Framework o di Windows Runtime per creare un metodo asincrono con la stessa facilità con cui è possibile creare un metodo sincrono. I metodi asincroni definiti mediante `Async` e `Await` sono denominati metodi asincroni.

Nell'esempio seguente viene illustrato un metodo asincrono. Quasi tutti gli elementi del codice dovrebbe essere completamente noti all'utente. I commenti richiamano le funzionalità che si aggiungono per creare la modalità asincrona.

È possibile trovare il file di esempio completo Windows Presentation Foundation (WPF) alla fine di questo argomento e scaricare l'esempio dalla pagina [Async Sample: Example from "Asynchronous Programming with Async and Await"](https://docs.microsoft.com/samples/dotnet/samples/async-and-await-vb/) (Esempio di attività asincrona: Programmazione asincrona con async e await).

```vb
' Three things to note about writing an Async Function:
'  - The function has an Async modifier.
'  - Its return type is Task or Task(Of T). (See "Return Types" section.)
'  - As a matter of convention, its name ends in "Async".
Async Function AccessTheWebAsync() As Task(Of Integer)
    Using client As New HttpClient()
        ' Call and await separately.
        '  - AccessTheWebAsync can do other things while GetStringAsync is also running.
        '  - getStringTask stores the task we get from the call to GetStringAsync.
        '  - Task(Of String) means it is a task which returns a String when it is done.
        Dim getStringTask As Task(Of String) =
            client.GetStringAsync("https://docs.microsoft.com/dotnet")
        ' You can do other work here that doesn't rely on the string from GetStringAsync.
        DoIndependentWork()
        ' The Await operator suspends AccessTheWebAsync.
        '  - AccessTheWebAsync does not continue until getStringTask is complete.
        '  - Meanwhile, control returns to the caller of AccessTheWebAsync.
        '  - Control resumes here when getStringTask is complete.
        '  - The Await operator then retrieves the String result from getStringTask.
        Dim urlContents As String = Await getStringTask
        ' The Return statement specifies an Integer result.
        ' A method which awaits AccessTheWebAsync receives the Length value.
        Return urlContents.Length

    End Using

End Function
```

Se `AccessTheWebAsync` non ha alcuna operazione da eseguire tra la chiamata di `GetStringAsync` e il relativo completamento, è possibile semplificare il codice chiamando l'istruzione singola seguente e rimanendo in attesa.

```vb
Dim urlContents As String = Await client.GetStringAsync()
```

Le seguenti caratteristiche riepilogano gli elementi che rendono l'esempio precedente un metodo asincrono:

- La firma del metodo include un modificatore `Async`.
- Il nome di un metodo asincrono termina per convenzione con un suffisso "Async".
- Il tipo restituito è uno dei seguenti:

  - [Task (Of TResult)](xref:System.Threading.Tasks.Task%601) se il metodo dispone di un'istruzione return in cui l'operando è di tipo TResult.
  - <xref:System.Threading.Tasks.Task> se nel metodo non è presente un'istruzione return oppure è presente un'istruzione return senza l'operando.
  - [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) se si sta scrivendo un gestore eventi asincrono.

  Per ulteriori informazioni, vedere la sezione "Tipi restituiti e parametri" più avanti in questo argomento.

- Il metodo include in genere almeno un'espressione await, che contrassegna un punto in cui il metodo non può continuare fino a quando l'operazione asincrona attesa non sia completata. Nel frattempo, il metodo viene sospeso e il controllo ritorna al chiamante del metodo. Nella sezione successiva di questo argomento viene illustrato quello che accade in corrispondenza del punto di sospensione.

Nei metodi asincroni utilizzare le parole chiave e i tipi forniti per indicare l'operazione da eseguire e il compilatore esegue il resto dell'operazione, inclusa la traccia di cosa deve verificarsi quando il controllo viene restituito a un punto di attesa in un metodo sospeso. Alcuni processi di routine, come cicli e gestione delle eccezioni, possono essere difficili da gestire nel codice asincrono tradizionale. In un metodo asincrono scrivere questi elementi come in una soluzione sincrona e il problema viene risolto.

Per altre informazioni sulla modalità asincrona in versioni precedenti di .NET Framework, vedere [TPL and Traditional .NET Framework Asynchronous Programming](../../../../standard/parallel-programming/tpl-and-traditional-async-programming.md) (TPL e programmazione asincrona .NET Framework tradizionale).

## <a name="BKMK_WhatHappensUnderstandinganAsyncMethod"></a>Cosa accade in un metodo asincrono

La cosa più importante da capire nella programmazione asincrona è il modo in cui il flusso del controllo si sposta da un metodo all'altro. Nel diagramma seguente viene descritto il processo:

![Diagramma che illustra la traccia di un programma asincrono.](./media/index/navigation-trace-async-program.png)

I numeri nel diagramma corrispondono ai passaggi seguenti:

1. Un gestore eventi chiama e attende il `AccessTheWebAsync` metodo asincrono.

2. `AccessTheWebAsync` crea un'istanza di <xref:System.Net.Http.HttpClient> e chiama il metodo asincrono <xref:System.Net.Http.HttpClient.GetStringAsync%2A> per scaricare il contenuto di un sito Web come stringa.

3. Si verifica un evento in `GetStringAsync` che ne sospende lo stato di avanzamento forse perché deve attendere il termine dello scaricamento di un sito Web o un'altra attività di blocco. Per evitare di bloccare le risorse, `GetStringAsync` restituisce il controllo al chiamante `AccessTheWebAsync`.

     `GetStringAsync` restituisce un' [attività (Of TResult)](xref:System.Threading.Tasks.Task%601) in cui TResult è una stringa e `AccessTheWebAsync` assegna l'attività alla variabile `getStringTask`. L'attività rappresenta il processo in corso per la chiamata a `GetStringAsync`, con l'impegno di produrre un valore stringa effettivo a completamento del lavoro.

4. Poiché `getStringTask` non è stata ancora attesa, `AccessTheWebAsync` può continuare con altro lavoro che non dipende dal risultato finale ottenuto da `GetStringAsync`. Tale lavoro è rappresentato da una chiamata al metodo sincrono `DoIndependentWork`.

5. `DoIndependentWork` è un metodo sincrono che esegue il proprio lavoro e lo restituisce al chiamante.

6. `AccessTheWebAsync` ha esaurito il lavoro che può eseguire senza un risultato da `getStringTask`. `AccessTheWebAsync` deve quindi calcolare e restituire la lunghezza della stringa scaricata, ma il metodo non può calcolare il valore finché quest'ultimo non contiene la stringa.

     Di conseguenza, `AccessTheWebAsync` utilizza un operatore await per sospendere lo stato di avanzamento e restituire il controllo al metodo che ha chiamato `AccessTheWebAsync`. `AccessTheWebAsync` restituisce `Task(Of Integer)` al chiamante. L'attività rappresenta l'intenzione di produrre un risultato di tipo Integer che è la lunghezza della stringa scaricata.

    > [!NOTE]
    > Se l'operazione `GetStringAsync` (e quindi `getStringTask`) viene completata prima che `AccessTheWebAsync` ne attenda il risultato, il controllo resta a `AccessTheWebAsync`. I costi per sospendere e tornare a `AccessTheWebAsync` sarebbero sprecati se il processo asincrono chiamato (`getStringTask`) fosse già completato e AccessTheWebSync non dovesse attendere il risultato finale.

     Nel chiamante (in questo esempio il gestore eventi), il modello di elaborazione continua. Il chiamante può eseguire altre attività che non dipendono dal risultato di `AccessTheWebAsync` prima di attendere tale risultato oppure può mettersi immediatamente in attesa.   Il gestore eventi è in attesa di `AccessTheWebAsync` e `AccessTheWebAsync` è in attesa di `GetStringAsync`.

7. `GetStringAsync` termina e produce un risultato di stringa. Il risultato di stringa non viene restituito dalla chiamata a `GetStringAsync` nel modo previsto. Tenere presente che il metodo non ha restituito un'attività al passaggio 3. Il risultato di stringa viene invece memorizzato nell'attività che rappresenta il completamento del metodo, ovvero `getStringTask`. L'operatore await recupera il risultato da `getStringTask`. L'istruzione di assegnazione assegna il risultato recuperato a `urlContents`.

8. Quando `AccessTheWebAsync` ha il risultato di stringa, il metodo può calcolare la lunghezza della stringa. Il lavoro di `AccessTheWebAsync` è quindi completo e il gestore eventi in attesa può riprendere l'attività. Nell'esempio completo alla fine dell'argomento è possibile confermare che il gestore eventi recupera e stampa il valore del risultato di lunghezza.

Se non si ha familiarità con la programmazione asincrona, valutare la differenza tra il comportamento sincrono e asincrono. Viene restituito un metodo sincrono quando il lavoro è completato (passaggio 5), ma un metodo asincrono restituisce un valore di attività quando il relativo lavoro viene sospeso (passaggi 3 e 6). Una volta che il metodo asincrono completa l'operazione, l'attività viene contrassegnata come completata e il risultato, se disponibile, viene archiviato nell'attività.

Per altre informazioni sul flusso di controllo, vedere [Flusso di controllo in programmi asincroni (Visual Basic)](control-flow-in-async-programs.md).

## <a name="BKMK_APIAsyncMethods"></a> Metodi asincroni per API

Metodi come `GetStringAsync` che supportano la programmazione asincrona Il .NET Framework 4,5 o versione successiva contiene molti membri che funzionano con `Async` e `Await`. È possibile riconoscere questi membri dal suffisso "Async" associato al nome del membro e da un tipo restituito di <xref:System.Threading.Tasks.Task> o [Task (Of TResult)](xref:System.Threading.Tasks.Task%601). Ad esempio, la classe `System.IO.Stream` contiene metodi come <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.ReadAsync%2A> e <xref:System.IO.Stream.WriteAsync%2A> insieme ai metodi sincroni <xref:System.IO.Stream.CopyTo%2A>, <xref:System.IO.Stream.Read%2A> e <xref:System.IO.Stream.Write%2A>.

Windows Runtime contiene inoltre molti metodi che è possibile usare con `Async` e `Await` in app Windows. Per altre informazioni e metodi di esempio, vedere [chiamare le API C# asincrone in o Visual Basic](/windows/uwp/threading-async/call-asynchronous-apis-in-csharp-or-visual-basic), [programmazione asincrona (app Windows Runtime)](https://docs.microsoft.com/previous-versions/windows/apps/hh464924(v=win.10))e [WhenAny: bridging tra la .NET Framework e la Windows Runtime](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/jj635140(v=vs.120)).

## <a name="BKMK_Threads"></a> Thread

I metodi asincroni vengono considerati operazioni non bloccanti. Un'espressione `Await` in un metodo asincrono non blocca il thread corrente quando l'attività attesa è in esecuzione. Al contrario, l'espressione registra il resto del metodo come continuazione e restituisce il controllo al chiamante del metodo asincrono.

Le parole chiave `Async` e `Await` non determinano la creazione di thread aggiuntivi. I metodi asincroni non richiedono il multithreading perché un metodo asincrono non viene eseguito nel proprio thread. Il metodo viene eseguito nel contesto di sincronizzazione corrente e utilizza il tempo sul thread solo se il metodo è attivo. È possibile utilizzare <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> per spostare un lavoro associato alla CPU in un thread in background. Quest'ultimo tuttavia non è di alcun ausilio in un processo che attende solo che i risultati diventino disponibili.

L'approccio alla programmazione asincrona basato su async è quasi sempre preferibile agli approcci esistenti. In particolare, questo approccio è migliore rispetto a <xref:System.ComponentModel.BackgroundWorker> per le operazioni di I/O perché il codice è più semplice e non è necessario proteggersi da race condition. Insieme a <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType>, la programmazione asincrona è migliore di <xref:System.ComponentModel.BackgroundWorker> per le operazioni associate alla CPU perché separa i dettagli di coordinamento per l'esecuzione del codice dal lavoro che `Task.Run` trasferisce al pool di thread.

## <a name="BKMK_AsyncandAwait"></a> Async e Await

Se si specifica che un metodo è asincrono usando un modificatore [Async](../../../../visual-basic/language-reference/modifiers/async.md), vengono attivate le due funzionalità seguenti.

- Il metodo asincrono contrassegnato può usare [Await](../../../../visual-basic/language-reference/operators/await-operator.md) per definire i punti di sospensione. L'operatore await indica al compilatore che il metodo asincrono non può continuare oltre un dato punto prima del completamento del processo asincrono in attesa. Nel frattempo il controllo viene restituito al chiamante del metodo asincrono.

  La sospensione di un metodo asincrono in un'espressione `Await` non costituisce un'uscita dal metodo e i blocchi `Finally` non vengono eseguiti.

- Il metodo asincrono contrassegnato può essere atteso da metodi che lo chiamano.

Un metodo asincrono contiene in genere una o più occorrenze di un operatore di `Await`, ma l'assenza di espressioni `Await` non provoca un errore del compilatore. Se un metodo asincrono non usa un operatore `Await` per contrassegnare un punto di sospensione, il metodo viene eseguito come metodo sincrono, nonostante il modificatore di `Async`. Il compilatore genera un avviso per tali metodi.

`Async` e `Await` sono parole chiave contestuali. Per ulteriori informazioni ed esempi, vedere gli argomenti seguenti:

- [Async](../../../../visual-basic/language-reference/modifiers/async.md)
- [Operatore Await](../../../../visual-basic/language-reference/operators/await-operator.md)

## <a name="BKMK_ReturnTypesandParameters"></a> Tipi restituiti e parametri

Nella programmazione .NET Framework un metodo asincrono restituisce in genere una <xref:System.Threading.Tasks.Task> o un' [attività (Of TResult)](xref:System.Threading.Tasks.Task%601). In un metodo asincrono un operatore `Await` viene applicato a un'attività restituita da una chiamata a un altro metodo asincrono.

È possibile specificare [Task (Of TResult)](xref:System.Threading.Tasks.Task%601) come tipo restituito se il metodo contiene un'istruzione [Return](../../../../visual-basic/language-reference/statements/return-statement.md) che specifica un operando di tipo `TResult`.

Utilizzare `Task` come tipo restituito se il metodo non include un'istruzione return o contiene un'istruzione return che non restituisce un operando.

Nell'esempio seguente viene illustrato come dichiarare e chiamare un metodo che restituisce un' [attività (Of TResult)](xref:System.Threading.Tasks.Task%601) o un <xref:System.Threading.Tasks.Task>:

```vb
' Signature specifies Task(Of Integer)
Async Function TaskOfTResult_MethodAsync() As Task(Of Integer)

    Dim hours As Integer
    ' . . .
    ' Return statement specifies an integer result.
    Return hours
End Function

' Calls to TaskOfTResult_MethodAsync
Dim returnedTaskTResult As Task(Of Integer) = TaskOfTResult_MethodAsync()
Dim intResult As Integer = Await returnedTaskTResult
' or, in a single statement
Dim intResult As Integer = Await TaskOfTResult_MethodAsync()

' Signature specifies Task
Async Function Task_MethodAsync() As Task

    ' . . .
    ' The method has no return statement.
End Function

' Calls to Task_MethodAsync
Task returnedTask = Task_MethodAsync()
Await returnedTask
' or, in a single statement
Await Task_MethodAsync()
```

Ogni attività restituita rappresenta il lavoro attualmente in fase di esecuzione. Un'attività include le informazioni sullo stato del processo asincrono e, infine, il risultato finale del processo o l'eccezione che il processo genera se non viene completato.

Un metodo asincrono può essere anche un metodo `Sub`. Il tipo restituito viene usato principalmente per definire i gestori eventi, dove è necessario un tipo restituito. I gestori eventi asincroni fungono spesso da punto di partenza per i programmi asincroni.

Un metodo asincrono che è una routine di `Sub` non può essere atteso e il chiamante non può intercettare le eccezioni generate dal metodo.

Un metodo asincrono non può dichiarare parametri [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), ma può chiamare metodi che hanno tali parametri.

Per altre informazioni ed esempi, vedere [Tipi restituiti asincroni (Visual Basic)](async-return-types.md). Per altre informazioni su come intercettare eccezioni nei metodi asincroni, vedere [Istruzione Try...Catch...Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).

Nella programmazione Windows Runtime le API asincrone hanno uno dei tipi restituiti seguenti, che sono simili alle attività:

- [IAsyncOperation (Of TResult)](xref:Windows.Foundation.IAsyncOperation%601), che corrisponde a [Task (Of TResult)](xref:System.Threading.Tasks.Task%601)
- <xref:Windows.Foundation.IAsyncAction>, che corrisponde a <xref:System.Threading.Tasks.Task>
- [IAsyncActionWithProgress (di TProgress)](xref:Windows.Foundation.IAsyncActionWithProgress%601)
- [IAsyncOperationWithProgress (Of TResult, TProgress)](xref:Windows.Foundation.IAsyncOperationWithProgress%602)

Per ulteriori informazioni e un esempio, vedere [chiamare le API asincrone C# in o Visual Basic](/windows/uwp/threading-async/call-asynchronous-apis-in-csharp-or-visual-basic).

## <a name="BKMK_NamingConvention"></a> Convenzione di denominazione

Per convenzione, il suffisso "Async" viene aggiunto ai nomi dei metodi che presentano un modificatore `Async`.

È possibile ignorare la convenzione se un evento, una classe base o un contratto di interfaccia suggerisce un nome diverso. Ad esempio, non è necessario rinominare i gestori eventi comuni, ad esempio `Button1_Click`.

## <a name="BKMK_RelatedTopics"></a> Argomenti correlati ed esempi (Visual Studio)

|Titolo|Descrizione|Esempio|
|-----------|-----------------|------------|
|[Procedura dettagliata: Accesso al Web con Async e Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md)|Mostra come convertire una soluzione WPF sincrona in una soluzione WPF asincrona. L'applicazione scarica una serie di siti Web.|[Async Sample: Accessing the Web Walkthrough](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) (Esempio di attività asincrona: Accesso alla procedura dettagliata Web)|
|[Procedura: Estendere la procedura dettagliata asincrona tramite Task.WhenAll (Visual Basic)](how-to-extend-the-async-walkthrough-by-using-task-whenall.md)|Aggiunge <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> alla procedura dettagliata precedente. L'utilizzo di `WhenAll` consente di avviare tutti i download contemporaneamente.||
|[Procedura: Eseguire più richieste Web in parallelo tramite async e await (Visual Basic)](how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)|Viene illustrato come avviare contemporaneamente diverse attività.|[Async Sample: Make Multiple Web Requests in Parallel](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e) (Esempio di attività asincrona: Esecuzione di più richieste Web in parallelo)|
|[Tipi restituiti asincroni (Visual Basic)](async-return-types.md)|Vengono illustrati i tipi che i metodi asincroni possono restituire e viene spiegato quando ogni tipo è appropriato.||
|[Flusso di controllo in programmi asincroni (Visual Basic)](control-flow-in-async-programs.md)|Traccia in dettaglio il flusso di controllo con una successione di espressioni await in un programma asincrono.|[Async Sample: Control Flow in Async Programs](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0) (Esempio di attività asincrona: Flusso di controllo in programmi asincroni)|
|[Ottimizzazione dell'applicazione Async (Visual Basic)](fine-tuning-your-async-application.md)|Mostra come aggiungere la seguente funzionalità alla soluzione asincrono:<br /><br /> - [Annullare un'attività asincrona o un elenco di attività (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md)<br />- [Annullare attività asincrone dopo un periodo di tempo (Visual Basic)](cancel-async-tasks-after-a-period-of-time.md)<br />- [Annullare le attività asincrone rimanenti dopo che ne è stata completata una(Visual Basic)](cancel-remaining-async-tasks-after-one-is-complete.md)<br />- [Avviare più attività asincrone ed elaborarle quando vengono completate (Visual Basic)](start-multiple-async-tasks-and-process-them-as-they-complete.md)|[Async Sample: Fine Tuning Your Application](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea) (Esempio di attività asincrona: Ottimizzazione dell'applicazione)|
|[Gestione della reentrancy nelle applicazioni asincrone (Visual Basic)](handling-reentrancy-in-async-apps.md)|Viene illustrato come gestire i casi in cui un'operazione asincrona attiva viene riavviata mentre è in esecuzione.||
|[WhenAny: bridging tra .NET Framework e Windows Runtime](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/jj635140(v=vs.120))|Descrive come integrare i tipi di attività in .NET Framework e IAsyncOperations in Windows Runtime per usare <xref:System.Threading.Tasks.Task.WhenAny%2A> con un metodo di Windows Runtime.|[Async Sample: Bridging between .NET and Windows Runtime (AsTask and WhenAny)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/jj635140(v=vs.120)) (Esempio di attività asincrona: Bridging tra .NET e Windows Runtime (AsTask e WhenAny))|
|Annullamento asincrono: bridging tra .NET Framework e Windows Runtime|Descrive come integrare i tipi di attività in .NET Framework e IAsyncOperations in Windows Runtime per usare <xref:System.Threading.CancellationTokenSource> con un metodo di Windows Runtime.|[Async Sample: Bridging between .NET and Windows Runtime (AsTask & Cancellation)](https://code.msdn.microsoft.com/Async-Sample-Bridging-9479eca3) (Esempio di attività asincrona: Bridging tra .NET e Windows Runtime (AsTask e Cancellation))|
|[Uso della funzionalità Async per l'accesso ai file (Visual Basic)](using-async-for-file-access.md)|Vengono elencati e illustrati i vantaggi dell'utilizzo di async e await per accedere ai file.||
|[Modello asincrono basato su attività (TAP)](../../../../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)|Descrive un nuovo modello per la modalità asincrona in .NET Framework. Il modello è basato sui tipi <xref:System.Threading.Tasks.Task> e [Task (Of TResult)](xref:System.Threading.Tasks.Task%601) .||
|[Video sulla modalità asincrona su Channel 9](https://channel9.msdn.com/search?term=async+&type=All)|Vengono forniti collegamenti a una serie di video sulla programmazione asincrona.||

## <a name="BKMK_CompleteExample"></a> Esempio completo

Il codice seguente rappresenta il file MainWindow.xaml.vb dell'applicazione Windows Presentation Foundation (WPF) discussa in questo argomento. È possibile scaricare l'esempio dalla pagina [Async Sample: Example from "Asynchronous Programming with Async and Await"](https://docs.microsoft.com/samples/dotnet/samples/async-and-await-vb/) (Esempio di attività asincrona: Programmazione asincrona con async e await).

[!code-vb[async](~/samples/async/async-and-await/vb/MainWindow.xaml.vb)]

## <a name="see-also"></a>Vedere anche

- [Operatore Await](../../../../visual-basic/language-reference/operators/await-operator.md)
- [Async](../../../../visual-basic/language-reference/modifiers/async.md)
