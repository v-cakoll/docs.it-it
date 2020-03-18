---
title: Funzioni di Azure durevoli - App senza server
description: Le funzioni di Azure durevoli estendono il runtime di Funzioni di Azure per abilitare flussi di lavoro con stato nel codice.
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 2c0ad086640409ac187c3aa882add4d6b39b6ff9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522859"
---
# <a name="durable-azure-functions"></a>Funzioni Durable di Azure

Quando si creano applicazioni senza server con Funzioni di Azure, le operazioni verranno in genere progettate per essere eseguite in modo senza stato. La ragione di questa scelta di progettazione è perché come la piattaforma scala, diventa difficile sapere su quali server il codice è in esecuzione su. Diventa anche difficile sapere quanti istanze sono attivi in un dato punto. Tuttavia, esistono classi di applicazioni che richiedono lo stato corrente di un processo da conoscere. Considerare il processo di invio di un ordine a un negozio online. L'operazione di estrazione può essere un flusso di lavoro composto da più operazioni che devono conoscere lo stato del processo. Tali informazioni possono includere l'inventario del prodotto, se il cliente ha crediti sul proprio conto, none i risultati dell'elaborazione della carta di credito. Queste operazioni potrebbero facilmente essere i propri flussi di lavoro interni o anche i servizi da sistemi di terze parti.

Oggi esistono vari modelli che aiutano con il coordinamento dello stato dell'applicazione tra sistemi interni ed esterni. È comune imbattersi in soluzioni che si basano su sistemi di accodamento centralizzati, archivi con valori di chiave distribuiti o database condivisi per gestire tale stato. Tuttavia, si tratta di tutte risorse aggiuntive che devono ora essere sottoposte a provisioning e gestite. In un ambiente senza server, il codice potrebbe diventare ingombrante nel tentativo di coordinarsi con queste risorse manualmente. Funzioni di Azure offre un'alternativa per la creazione di funzioni con stato denominate funzioni durevoli.

Funzioni durevoli è un'estensione del runtime di Funzioni di Azure che consente la definizione di flussi di lavoro con stato nel codice. Suddividendo i flussi di lavoro in attività, l'estensione Funzioni permanenti può gestire lo stato, creare checkpoint di stato e gestire la distribuzione delle chiamate di funzione tra i server. In background, usa un account di Archiviazione di Azure per rendere persistente la cronologia di esecuzione, pianificare le funzioni di attività e recuperare le risposte. Il codice senza server non deve mai interagire con le informazioni persistenti nell'account di archiviazione e in genere non è un elemento con cui gli sviluppatori devono interagire.

## <a name="triggering-a-stateful-workflow"></a>Attivazione di un flusso di lavoro con statoTriggering a stateful workflow

I flussi di lavoro con stato in Funzioni durevoli possono essere suddivisi in due componenti intrinseci; trigger di orchestrazione e attività. I trigger e le associazioni sono componenti di base usati da Funzioni di Azure per consentire alle funzioni senza server di ricevere notifiche quando avviare, ricevere l'input e restituire i risultati.

### <a name="working-with-the-orchestration-client"></a>Utilizzo del client di orchestrazione

Le orchestrazioni sono univoche rispetto ad altri stili di operazioni attivate in Funzioni di Azure.Orchestrations are unique when compared to other styles of triggered operations in Azure Functions. Funzioni durevoli consente l'esecuzione di funzioni che possono richiedere ore o addirittura giorni per essere completate. Questo tipo di comportamento include la necessità di controllare lo stato di un'orchestrazione in esecuzione, terminare preventivamente o inviare notifiche di eventi esterni.

In questi casi, l'estensione `DurableOrchestrationClient` Funzioni permanenti fornisce la classe che consente di interagire con funzioni orchestrate. È possibile accedere al client di `OrchestrationClientAttribute` orchestrazione utilizzando l'associazione. In genere, questo attributo viene incluso `HttpTrigger` con `ServiceBusTrigger`un altro tipo di trigger, ad esempio un oggetto o . Dopo aver attivato la funzione di origine, il client di orchestrazione può essere utilizzato per avviare una funzione dell'agente di orchestrazione.

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

### <a name="the-orchestrator-function"></a>La funzione dell'agente di orchestrazione

Annotare una funzione con OrchestrationTriggerAttribute in Funzioni di Azure contrassegna che funzionano come una funzione dell'agente di orchestrazione. È responsabile della gestione delle varie attività che costituiscono il flusso di lavoro con stato.

Le funzioni dell'agente di orchestrazione non sono in grado di utilizzare associazioni diverse da OrchestrationTriggerAttribute.Orchestrator functions are unable to use of bindings other than the OrchestrationTriggerAttribute. Questo attributo può essere utilizzato solo con un tipo di parametro DurableOrchestrationContext.This attribute can only be used with a parameter type of DurableOrchestrationContext. Non è possibile utilizzare altri input poiché la deserializzazione degli input nella firma della funzione non è supportata. Per ottenere gli input forniti dal client di\<\> orchestrazione, è necessario utilizzare il metodo GetInput T.

Inoltre, i tipi restituiti delle funzioni di orchestrazione devono essere void, Task o un valore serializzabile JSON.

> *Il codice di gestione degli errori è stato escluso per brevità*

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

È possibile avviate e in esecuzione più istanze di un'orchestrazione contemporaneamente. La `StartNewAsync` chiamata del `DurableOrchestrationClient` metodo all'avvio di una nuova istanza dell'orchestrazione. Il metodo `Task<string>` restituisce un che viene completato quando l'orchestrazione è stata avviata. Se l'orchestrazione non è stata avviata entro 30 secondi, viene generata un'eccezione di tipo. `TimeoutException`

Il `Task<string>` completato `StartNewAsync` da deve contenere l'ID univoco dell'istanza dell'orchestrazione. Questo ID istanza può essere utilizzato per richiamare operazioni su tale orchestrazione specifica. È possibile eseguire una query sull'orchestrazione per lo stato o per l'invio di notifiche di eventi.

### <a name="the-activity-functions"></a>Le funzioni di attività

Le funzioni di attività sono le operazioni discrete che vengono composte insieme all'interno di una funzione di orchestrazione per creare il flusso di lavoro. Qui è dove la maggior parte del lavoro effettivo avrebbe luogo. Rappresentano la logica di business, i processi a esecuzione prolungata e il puzzle si prepari in una soluzione più ampia.

Viene `ActivityTriggerAttribute` utilizzato per annotare un `DurableActivityContext`parametro di funzione di tipo . L'utilizzo dell'annotazione informa il runtime che la funzione deve essere utilizzata come funzione di attività. I valori di input alle `GetInput<T>` funzioni `DurableActivityContext` di attività vengono recuperati utilizzando il metodo del parametro.

Analogamente alle funzioni di orchestrazione, i tipi restituiti delle funzioni di attività devono essere void, Task o un valore serializzabile JSON.

Tutte le eccezioni non gestite generate all'interno delle funzioni di attività verranno inviate alla funzione dell'agente di orchestrazione chiamante e presentate come oggetto `TaskFailedException`. A questo punto, l'errore può essere intercettato e registrato nell'agente di orchestrazione e l'attività può essere ritentata.

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

- [Funzioni permanenti](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
- [Associazioni per funzioni durevoliBindings for Durable Functions](https://docs.microsoft.com/azure/azure-functions/durable-functions-bindings)
- [Gestire le istanze in Funzioni durevoliManage instances in Durable Functions](https://docs.microsoft.com/azure/azure-functions/durable-functions-instance-management)

>[!div class="step-by-step"]
>[Successivo](event-grid.md)
>[precedente](orchestration-patterns.md)
