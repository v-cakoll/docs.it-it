---
title: Funzioni di Azure durevoli-app senza server
description: Funzioni di Azure durevoli estendono il runtime di funzioni di Azure per abilitare i flussi di lavoro con stato nel codice.
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 2c0ad086640409ac187c3aa882add4d6b39b6ff9
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2019
ms.locfileid: "72522859"
---
# <a name="durable-azure-functions"></a>Funzioni Durable di Azure

Quando si creano applicazioni senza server con funzioni di Azure, le operazioni vengono in genere progettate per essere eseguite in modo senza stato. Il motivo di questa scelta di progettazione è che, con la scalabilità della piattaforma, diventa difficile conoscere i server in cui viene eseguito il codice. È anche difficile capire il numero di istanze attive in un determinato punto. Tuttavia, esistono classi di applicazioni che richiedono che lo stato corrente di un processo sia noto. Si consideri il processo di invio di un ordine a un negozio online. L'operazione di estrazione potrebbe essere un flusso di lavoro composto da più operazioni che devono essere a conoscenza dello stato del processo. Tali informazioni possono includere l'inventario del prodotto, se il cliente dispone di crediti sull'account e anche i risultati dell'elaborazione della carta di credito. Queste operazioni possono essere facilmente i propri flussi di lavoro interni o persino i servizi di sistemi di terze parti.

Attualmente esistono diversi modelli che assistono al coordinamento dello stato dell'applicazione tra sistemi interni ed esterni. Sono comuni le soluzioni che si basano su sistemi di Accodamento centralizzati, archivi chiave-valore distribuiti o database condivisi per gestire tale stato. Tuttavia, si tratta di risorse aggiuntive che ora è necessario eseguire il provisioning e la gestione. In un ambiente senza server, il codice potrebbe diventare un tentativo complesso di coordinarsi con queste risorse manualmente. Funzioni di Azure offre un'alternativa per la creazione di funzioni con stato denominate Durable Functions.

Durable Functions è un'estensione del runtime di funzioni di Azure che consente la definizione di flussi di lavoro con stato nel codice. Suddividendo i flussi di lavoro in attività, l'estensione Durable Functions può gestire lo stato, creare checkpoint di stato e gestire la distribuzione delle chiamate di funzione tra i server. In background, viene usato un account di archiviazione di Azure per rendere permanente la cronologia di esecuzione, pianificare le funzioni di attività e recuperare le risposte. Il codice senza server non deve mai interagire con le informazioni salvate in modo permanente nell'account di archiviazione e non è in genere un elemento con cui gli sviluppatori devono interagire.

## <a name="triggering-a-stateful-workflow"></a>Attivazione di un flusso di lavoro con stato

I flussi di lavoro con stato in Durable Functions possono essere suddivisi in due componenti intrinseci. trigger di orchestrazione e di attività. I trigger e le associazioni sono componenti di base usati da funzioni di Azure per consentire alle funzioni senza server di ricevere notifiche quando avviare, ricevere input e restituire risultati.

### <a name="working-with-the-orchestration-client"></a>Utilizzo del client di orchestrazione

Le orchestrazioni sono univoche rispetto ad altri stili di operazioni attivate in funzioni di Azure. Durable Functions consente l'esecuzione di funzioni che possono richiedere ore o persino giorni per il completamento. Questo tipo di comportamento prevede la necessità di poter controllare lo stato di un'orchestrazione in esecuzione, terminare preventivamente o inviare notifiche di eventi esterni.

In questi casi, l'estensione Durable Functions fornisce la classe `DurableOrchestrationClient` che consente di interagire con le funzioni orchestrate. Per ottenere l'accesso al client di orchestrazione, è possibile usare l'associazione `OrchestrationClientAttribute`. In genere, è necessario includere questo attributo con un altro tipo di trigger, ad esempio un `HttpTrigger` o `ServiceBusTrigger`. Una volta attivata la funzione di origine, è possibile utilizzare il client di orchestrazione per avviare una funzione dell'agente di orchestrazione.

```csharp
[FunctionName("KickOff")]
public static async Task<HttpResponseMessage> Run(
    [HttpTrigger(AuthorizationLevel.Function, "POST")]HttpRequestMessage req,
    [OrchestrationClient ] DurableOrchestrationClient<orchestrationClient>)
{
    OrderRequestData data = await req.Content.ReadAsAsync<OrderRequestData>();

    string instanceId = await orchestrationClient.StartNewAsync("PlaceOrder", data);

    return orchestrationClient.CreateCheckStatusResponse(req, instanceId);
}
```

### <a name="the-orchestrator-function"></a>Funzione dell'agente di orchestrazione

Annotare una funzione con OrchestrationTriggerAttribute in funzioni di Azure contrassegna che funziona come funzione dell'agente di orchestrazione. È responsabile della gestione delle varie attività che costituiscono il flusso di lavoro con stato.

Le funzioni dell'agente di orchestrazione non sono in grado di utilizzare binding diversi da OrchestrationTriggerAttribute. Questo attributo può essere utilizzato solo con un tipo di parametro DurableOrchestrationContext. Non è possibile usare altri input perché la deserializzazione degli input nella firma della funzione non è supportata. Per ottenere gli input forniti dal client di orchestrazione, è necessario utilizzare il metodo GetInput\<T\>.

Inoltre, i tipi restituiti delle funzioni di orchestrazione devono essere void, Task o un valore serializzabile JSON.

> *Il codice di gestione degli errori è stato lasciato per brevità*

```csharp
[FunctionName("PlaceOrder")]
public static async Task<string> PlaceOrder([OrchestrationTrigger] DurableOrchestrationContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    await context.CallActivityAsync<bool>("CheckAndReserveInventory", orderData);
    await context.CallActivityAsync<string>("ProcessPayment", orderData);

    string trackingNumber = await context.CallActivityAsync<string>("ScheduleShipping", orderData);
    await context.CallActivityAsync<string>("EmailCustomer", trackingNumber);

    return trackingNumber;
}
```

È possibile avviare ed eseguire contemporaneamente più istanze di un'orchestrazione. Chiamando il metodo `StartNewAsync` sul `DurableOrchestrationClient` viene avviata una nuova istanza dell'orchestrazione. Il metodo restituisce un `Task<string>` che viene completato quando l'orchestrazione è stata avviata. Viene generata un'eccezione di tipo `TimeoutException` se l'orchestrazione non è stata avviata entro 30 secondi.

Il `Task<string>` completato da `StartNewAsync` deve contenere l'ID univoco dell'istanza dell'orchestrazione. Questo ID istanza può essere utilizzato per richiamare le operazioni su un'orchestrazione specifica. Per l'orchestrazione è possibile eseguire query per lo stato o le notifiche degli eventi inviati.

### <a name="the-activity-functions"></a>Funzioni di attività

Le funzioni di attività sono le operazioni discrete che vengono composte insieme in una funzione di orchestrazione per creare il flusso di lavoro. Ecco dove si svolge la maggior parte del lavoro effettivo. Rappresentano la logica di business, i processi a esecuzione prolungata e le parti del puzzle a una soluzione più ampia.

Il `ActivityTriggerAttribute` viene utilizzato per annotare un parametro di funzione di tipo `DurableActivityContext`. L'uso dell'annotazione informa il runtime che la funzione deve essere usata come funzione di attività. I valori di input per le funzioni di attività vengono recuperati utilizzando il metodo `GetInput<T>` del parametro `DurableActivityContext`.

Analogamente alle funzioni di orchestrazione, i tipi restituiti delle funzioni di attività devono essere void, Task o un valore serializzabile JSON.

Eventuali eccezioni non gestite generate all'interno delle funzioni dell'attività vengono inviate alla funzione dell'agente di orchestrazione chiamante e presentate come `TaskFailedException`. A questo punto, l'errore può essere intercettato e registrato nell'agente di orchestrazione e l'attività può essere ritentata.

```csharp
[FunctionName("CheckAndReserveInventory")]
public static bool CheckAndReserveInventory([ActivityTrigger] DurableActivityContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    // Connect to inventory system and try to reserve items
    return true;
}
```

## <a name="recommended-resources"></a>Risorse consigliate

- [Durable Functions](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
- [Binding per Durable Functions](https://docs.microsoft.com/azure/azure-functions/durable-functions-bindings)
- [Gestire le istanze in Durable Functions](https://docs.microsoft.com/azure/azure-functions/durable-functions-instance-management)

>[!div class="step-by-step"]
>[Precedente](event-grid.md)
>[Successivo](orchestration-patterns.md)
