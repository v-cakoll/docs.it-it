---
title: Programmazione asincrona in C#
description: Panoramica del supporto del linguaggio C# per la programmazione asincrona con async, await, Task e Task<T>
ms.date: 06/04/2020
ms.openlocfilehash: 992ccd3a015653ea9ee13dfc309d47711ad0fca4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619715"
---
# <a name="asynchronous-programming-with-async-and-await"></a>Programmazione asincrona con async e await

Il [modello di programmazione asincrona (TAP) dell'attività](task-asynchronous-programming-model.md) fornisce un'astrazione sul codice asincrono. Scrivere il codice come sequenza di istruzioni secondo la normale procedura. È possibile leggere il codice come se ogni istruzione venisse completata prima che venga iniziata quella successiva. Il compilatore esegue una serie di trasformazioni poiché alcune delle istruzioni potrebbero essere eseguite e restituire <xref:System.Threading.Tasks.Task> che rappresenta il lavoro in corso.

L'obiettivo di questa sintassi consiste nell'abilitare un codice che viene letto come una sequenza di istruzioni ma viene eseguito in un ordine più complesso in base all'allocazione delle risorse esterne e al completamento dell'attività. Si tratta di un funzionamento analogo a quello in cui gli utenti specificano istruzioni per i processi che includono attività asincrone. In questo articolo si userà un esempio di istruzioni per la creazione di una colazione per vedere come le `async` `await` parole chiave e semplificano la motivazione del codice, che include una serie di istruzioni asincrone. Si procederà a scrivere istruzioni come quelle dell'elenco seguente per descrivere come preparare una colazione:

1. Versare una tazza di caffè.
1. Scaldare una padella e friggere due uova.
1. Friggere tre fette di pancetta.
1. Tostare due fette di pane.
1. Aggiungere burro e marmellata alla fetta di pane tostata.
1. Versare un bicchiere di succo d'arancia.

Se si ha esperienza in cucina, queste istruzioni verranno eseguite **in modo asincrono**. Si inizierà a scaldare la padella per le uova e si inizierà a cuocere la pancetta. Si inserirà il pane nel tostapane, quindi si inizieranno a cuocere le uova. A ogni passaggio del processo si inizia un'attività, quindi ci si dedica alle attività che man mano richiedono attenzione.

La preparazione della colazione è un buon esempio di lavoro asincrono non parallelo. Tutte le attività possono essere gestite da una sola persona (o thread). Continuando con l'analogia della colazione, una sola persona può preparare la colazione in modo asincrono iniziando l'attività successiva prima che l'attività precedente venga completata. La preparazione procede indipendentemente dal fatto che venga controllata da qualcuno. Non appena si inizia a scaldare la padella per le uova, è possibile iniziare a friggere la pancetta. Dopo aver iniziato a cuocere la pancetta, è possibile inserire il pane nel tostapane.

In un algoritmo parallelo sarebbero necessari più cuochi (o thread). Un cuoco cucinerebbe le uova, un cuoco cucinerebbe la pancetta e così via. Ogni cuoco si dedicherebbe a una singola attività. Ogni cuoco (o thread) verrebbe bloccato in modo sincrono in attesa che la pancetta sia pronta per essere girata o che la tostatura del pane venga completata.

A questo punto, prendere in esame le stesse istruzioni scritte sotto forma di istruzioni C#:

:::code language="csharp" source="snippets/index/AsyncBreakfast-starter/Program.cs" highlight="8-27":::

:::image type="content" source="media/synchronous-breakfast.png" alt-text="colazione sincrona":::

La colazione preparata in modo sincrono richiede circa 30 minuti perché il totale è la somma di ogni singola attività.

> [!NOTE]
> Le `Coffee` `Egg` classi,, `Bacon` , `Toast` e `Juice` sono vuote. Sono semplicemente classi marcatore per lo scopo della dimostrazione, non contengono proprietà e non servono altri scopi.

I computer non interpretano le istruzioni allo stesso modo delle persone. Il computer si bloccherà in corrispondenza di ogni istruzione fino a quando non verrà completata prima di passare all'istruzione successiva. In questo modo non verrà preparata una colazione soddisfacente. Le attività successive non verranno iniziate prima del completamento delle attività precedenti. La preparazione della colazione richiederà più tempo e alcuni alimenti si raffredderanno prima di essere serviti.

Se si vuole che il computer esegua le istruzioni precedenti in modo asincrono, è necessario scrivere codice asincrono.

Queste considerazioni sono importanti per l'attuale scrittura dei programmi. Quando si scrivono programmi client, si vuole che l'interfaccia utente risponda all'input dell'utente. L'applicazione non deve bloccare l'uso del telefono durante il download di dati dal Web. Quando si scrivono programmi server, non si vuole che i thread vengano bloccati. I thread potrebbero essere impegnati a rispondere ad altre richieste. L'uso di codice sincrono quando sono presenti alternative asincrone riduce la possibilità di aumentare le istanze in modo meno costoso. I thread bloccati hanno un costo.

Per applicazioni moderne efficienti è necessario creare codice asincrono. Senza supporto del linguaggio, la scrittura di codice asincrono richiedeva callback, eventi di completamento o altri elementi che nascondevano la finalità originale del codice. Il vantaggio del codice sincrono risiede nella semplicità di comprensione. Le azioni passo passo rendono più semplice l'analisi e la comprensione. Nei modelli asincroni tradizionali era necessario porre l'attenzione sulla natura asincrona del codice anziché sulle azioni fondamentali del codice.

## <a name="dont-block-await-instead"></a>Non bloccare, ma attendere

Il codice precedente illustra una prassi non corretta, ovvero la costruzione di codice sincrono per eseguire operazioni asincrone. Come previsto, questo codice impedisce al thread che lo esegue di eseguire altre operazioni. Non verrà interrotto mentre un'attività è in corso. Equivale a mettersi a osservare il tostapane dopo avere inserito il pane. E a ignorare qualsiasi interlocutore fino a quando il pane non è pronto.

Si procederà ora ad aggiornare il codice in modo che il thread non venga bloccato mentre sono in esecuzione altre attività. La parola chiave `await` consente di iniziare un'attività senza alcun blocco e di continuare l'esecuzione al completamento dell'attività. Una versione asincrona semplice del codice della preparazione della colazione sarebbe simile al frammento seguente:

:::code language="csharp" source="snippets/index/AsyncBreakfast-V2/Program.cs" id="SnippetMain":::

> [!IMPORTANT]
> Il tempo totale trascorso è approssimativamente uguale a quello della versione iniziale di Synchonous. Il codice è ancora in uso per sfruttare alcune delle funzionalità principali della programmazione asincrona.

> [!TIP]
> I corpi dei metodi di `FryEggsAsync` , `FryBaconAsync` e `ToastBreadAsync` sono stati aggiornati per restituire `Task<Egg>` `Task<Bacon>` rispettivamente, e `Task<Toast>` . I metodi vengono rinominati dalla versione originale per includere il suffisso "Async". Le rispettive implementazioni vengono visualizzate come parte della [versione finale](#final-version) più avanti in questo articolo.

Questo codice non si blocca durante la cottura delle uova o della pancetta. Il codice tuttavia non inizia altre attività. Si inserisce il pane nel tostapane e si rimane a osservarlo fino al completamento della cottura. Ma almeno si risponde a un interlocutore che richiede attenzione. In un ristorante in cui vengono fatte più ordinazioni, il cuoco può iniziare a preparare un'altra colazione mentre la prima è in cottura.

Il thread impegnato nella preparazione della colazione non è bloccato in attesa che venga completata un'attività iniziata. Per alcune applicazioni, questa modifica è tutto ciò che serve. Un'applicazione GUI risponde sempre all'utente solo con questa modifica. Tuttavia, per questo scenario si desidera un altro funzionamento. Non si vuole che ogni attività del componente venga eseguita in modo sequenziale. È preferibile iniziare ogni attività del componente prima del completamento dell'attività precedente.

## <a name="start-tasks-concurrently"></a>Iniziare più attività contemporaneamente

In molti scenari si vuole iniziare immediatamente più attività indipendenti. Quindi, man mano che ogni attività viene terminata, è possibile passare ad altre operazioni da eseguire. Nell'analogia della colazione, questa modalità consente di preparare la colazione più rapidamente. Inoltre, tutte le operazioni vengono terminate quasi nello stesso momento. Si otterrà una colazione calda.

<xref:System.Threading.Tasks.Task?displayProperty=nameWithType> e i tipi correlati sono classi che è possibile usare per motivare le attività in corso. in questo modo è possibile scrivere codice più simile al modo in cui effettivamente si prepara una colazione. Si inizia a cuocere uova, pancetta e pane contemporaneamente. Man mano che ogni attività richiederà un'azione, si porrà l'attenzione su quell'attività, quindi sull'azione successiva e infine si rimarrà in attesa di altra attività da eseguire.

Si inizia un'attività e la si mantiene nell'oggetto <xref:System.Threading.Tasks.Task> che rappresenta il lavoro. Si rimarrà in attesa (`await`) di ogni attività prima di utilizzarne il risultato.

Verranno ora apportate queste modifiche al codice della colazione. Il primo passaggio consiste nell'archiviare le attività delle operazioni quando vengono iniziate, anziché rimanere in attesa di esse:

```csharp
Coffee cup = PourCoffee();
Console.WriteLine("coffee is ready");

Task<Egg> eggsTask = FryEggsAsync(2);
Egg eggs = await eggsTask;
Console.WriteLine("eggs are ready");

Task<Bacon> baconTask = FryBaconAsync(3);
Bacon bacon = await baconTask;
Console.WriteLine("bacon is ready");

Task<Toast> toastTask = ToastBreadAsync(2);
Toast toast = await toastTask;
ApplyButter(toast);
ApplyJam(toast);
Console.WriteLine("toast is ready");

Juice oj = PourOJ();
Console.WriteLine("oj is ready");
Console.WriteLine("Breakfast is ready!");
```

Successivamente, è possibile spostare le istruzioni `await` della pancetta e delle uova alla fine del metodo, prima di servire la colazione:

```csharp
Coffee cup = PourCoffee();
Console.WriteLine("coffee is ready");

Task<Egg> eggsTask = FryEggsAsync(2);
Task<Bacon> baconTask = FryBaconAsync(3);
Task<Toast> toastTask = ToastBreadAsync(2);

Toast toast = await toastTask;
ApplyButter(toast);
ApplyJam(toast);
Console.WriteLine("toast is ready");
Juice oj = PourOJ();
Console.WriteLine("oj is ready");

Egg eggs = await eggsTask;
Console.WriteLine("eggs are ready");
Bacon bacon = await baconTask;
Console.WriteLine("bacon is ready");

Console.WriteLine("Breakfast is ready!");
```

:::image type="content" source="media/asynchronous-breakfast.png" alt-text="colazione asincrona":::

La preparazione in modo asincrono ha richiesto circa 20 minuti perché alcune attività erano in grado di essere eseguite contemporaneamente.

Il codice precedente ha un funzionamento migliore. Tutte le attività asincrone vengono iniziate contemporaneamente. Si rimane in attesa di ogni attività solo quando è necessario avere a disposizione il risultato dell'attività. Il codice precedente potrebbe essere simile al codice di un'applicazione Web che effettua le richieste di diversi microservizi, quindi unisce i risultati in una singola pagina. Si eseguiranno tutte le richieste immediatamente, quindi si rimarrà in attesa (`await`) di tutte le attività e si comporrà la pagina Web.

## <a name="composition-with-tasks"></a>Composizione di attività

 Tutti gli alimenti della colazione sono pronti contemporaneamente ad eccezione del pane. La preparazione del pane rappresenta la composizione di un'operazione asincrona (tostatura del pane) e di operazioni sincrone (aggiunta del burro e della marmellata). L'aggiornamento di questo codice illustra un concetto importante:

> [!IMPORTANT]
> La composizione di un'operazione asincrona, seguita da un lavoro sincrono è un'operazione asincrona. In altre parole, se una parte di un'operazione è asincrona, l'intera operazione è asincrona.

Il codice precedente ha mostrato che è possibile usare gli oggetti <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> per attività in esecuzione. Si rimane in attesa (`await`) di ogni attività prima di usarne il risultato. Il passaggio successivo consiste nel creare metodi che rappresentano la combinazione di altre operazioni. Prima di servire la colazione, si vuole attendere l'attività che rappresenta la tostatura del pane prima dell'aggiunta del butto e della marmellata. È possibile rappresentare queste operazioni con il codice seguente:

:::code language="csharp" source="snippets/index/AsyncBreakfast-V3/Program.cs" id="SnippetComposeToastTask":::

Il metodo precedente include il modificatore `async` nella firma. Il modificatore segnala al compilatore che il metodo contiene un'istruzione `await`; contiene operazioni asincrone. Questo metodo rappresenta l'attività di tostatura del pane, quindi aggiunge il burro e la marmellata. Questo metodo restituisce <xref:System.Threading.Tasks.Task%601> che rappresenta la composizione di queste tre operazioni. Il blocco di codice principale sarà ora il seguente:

:::code language="csharp" source="snippets/index/AsyncBreakfast-V3/Program.cs" id="SnippetMain":::

La modifica precedente ha illustrato una tecnica importante per l'uso di codice asincrono. Si compongono le attività separando le operazioni in un nuovo metodo che restituisce un'attività. È possibile scegliere quando rimanere in attesa dell'attività. È possibile iniziare altre attività contemporaneamente.

## <a name="await-tasks-efficiently"></a>Attendere le attività in modo efficiente

La serie di istruzioni `await` alla fine del codice precedente può essere migliorata usando i metodi della classe `Task`. Una delle API è <xref:System.Threading.Tasks.Task.WhenAll%2A> che restituisce <xref:System.Threading.Tasks.Task> che viene completata quando tutte le attività del relativo elenco di argomenti sono state completate, come illustrato nel codice seguente:

```csharp
await Task.WhenAll(eggsTask, baconTask, toastTask);
Console.WriteLine("eggs are ready");
Console.WriteLine("bacon is ready");
Console.WriteLine("toast is ready");
Console.WriteLine("Breakfast is ready!");
```

Un'altra opzione consiste nell'usare <xref:System.Threading.Tasks.Task.WhenAny%2A> che restituisce `Task<Task>` che viene completata quando tutti i relativi argomenti vengono completati. È possibile attendere l'attività restituita, sapendo che è già stata completata. Il codice seguente illustra come è possibile usare <xref:System.Threading.Tasks.Task.WhenAny%2A> per attendere il completamento della prima attività e quindi elaborarne il risultato. Dopo aver elaborato il risultato dell'attività completata, si rimuove l'attività completata dall'elenco delle attività passate a `WhenAny`.

```csharp
var breakfastTasks = new List<Task> { eggsTask, baconTask, toastTask };
while (breakfastTasks.Count > 0)
{
    Task finishedTask = await Task.WhenAny(breakfastTasks);
    if (finishedTask == eggsTask)
    {
        Console.WriteLine("eggs are ready");
    }
    else if (finishedTask == baconTask)
    {
        Console.WriteLine("bacon is ready");
    }
    else if (finishedTask == toastTask)
    {
        Console.WriteLine("toast is ready");
    }
    breakfastTasks.Remove(finishedTask);
}
```

Dopo aver apportato tutte le modifiche, la versione finale del codice è simile alla seguente:<a id="final-version"></a>
:::code language="csharp" source="snippets/index/AsyncBreakfast-final/Program.cs" highlight="9-40":::

:::image type="content" source="media/whenany-async-breakfast.png" alt-text="Quando una qualsiasi colazione asincrona":::

La versione finale della colazione preparata in modo asincrono richiede circa 15 minuti, perché alcune attività possono essere eseguite simultaneamente e il codice è stato in grado di monitorare più attività contemporaneamente e di intervenire solo quando necessario.

Il codice finale è asincrono. Riflette con maggior precisione il modo in cui viene preparata una colazione. Confrontare il codice precedente con il primo esempio di codice di questo articolo. Le azioni principali risultano ancora chiare dalla lettura del codice. È possibile leggere il codice allo stesso modo in cui si leggerebbero le istruzioni per preparare una colazione riportate all'inizio di questo articolo. Le funzionalità del linguaggio per `async` e `await` offrono la traduzione che ogni persona farebbe per seguire le istruzioni scritte: iniziare le attività non appena possibile e non bloccarsi in attesa del completamento delle attività.

## <a name="next-steps"></a>Passaggi successivi

> [!div class="nextstepaction"]
> [Informazioni sul modello di programmazione asincrona delle attività](task-asynchronous-programming-model.md)
