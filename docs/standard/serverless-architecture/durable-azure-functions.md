---
title: Funzioni di Azure durevole - App senza server
description: Funzioni di Azure durevole estendono il runtime di funzioni di Azure per abilitare flussi di lavoro con stati nel codice.
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 03197ad57813b8132fe592f4e555c6a35edbd9bd
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2018
ms.locfileid: "49369954"
---
# <a name="durable-azure-functions"></a>Funzioni di Azure durevole

Quando si creano applicazioni senza server con funzioni di Azure, le operazioni saranno in genere progettate per l'esecuzione in modalità senza stata. Il motivo di tale scelta di progettazione è perché come aggiornare la piattaforma, diventa difficile sapere quali server in cui viene eseguito il codice. Inoltre, diventa difficile sapere quante istanze sono attive in qualsiasi momento. Tuttavia, esistono classi di applicazioni che richiedono lo stato corrente di un processo deve essere noto. Prendere in considerazione il processo di invio di un ordine a uno store online. L'operazione di checkpoint può essere un flusso di lavoro costituito da più operazioni che è necessario conoscere lo stato del processo. Tali informazioni possono includere nell'inventario dei prodotti, se il cliente ha eventuali crediti nel proprio account, nonché i risultati dell'elaborazione della carta di credito. Queste operazioni può essere facilmente i propri flussi di lavoro interni o persino servizi dai sistemi di terze parti.

Attualmente i vari modelli esistono fornire tale assistenza con il coordinamento di stato dell'applicazione tra i sistemi interni ed esterni. È raro riscontrare soluzioni che si basano su sistemi centralizzati di accodamento, distribuito gli archivi chiave-valore o i database condivisi per gestire tale stato. Tuttavia, queste sono tutte le altre risorse che devono ora essere eseguito il provisioning e gestite. In un ambiente senza server, il codice può diventare scomodo tenta di coordinare con queste risorse manualmente. Funzioni di Azure offre un'alternativa per la creazione di funzioni con state chiamate di funzioni permanenti.

Funzioni permanenti è un'estensione per il runtime di funzioni di Azure che consente la definizione dei flussi di lavoro con stati nel codice. Per scomporre i flussi di lavoro nelle attività, l'estensione funzioni permanenti può gestire lo stato, si creano checkpoint lo stato di avanzamento e gestire la distribuzione delle chiamate di funzione tra server. In background, fa uso di un account di archiviazione di Azure per rendere persistente la cronologia delle esecuzioni, pianificare le funzioni di attività e recuperare le risposte. Il codice senza server mai deve interagire con le informazioni persistenti nell'account di archiviazione e in genere non è un elemento con cui gli sviluppatori devono interagire.

## <a name="triggering-a-stateful-workflow"></a>Attivare un flusso di lavoro con stato

I flussi di lavoro con stati in funzioni permanenti può essere suddivisa in due componenti intrinseci. trigger di orchestrazione e l'attività. Trigger e associazioni sono componenti di base utilizzati dalle funzioni di Azure per consentire le funzioni senza server ricevere una notifica quando viene avviato, ricevere input e restituiscono risultati.

### <a name="working-with-the-orchestration-client"></a>Utilizzo del client di orchestrazione

Le orchestrazioni sono univoche rispetto agli altri stili di operazioni avviate in funzioni di Azure. Funzioni permanenti consente l'esecuzione di funzioni che potrebbero volerci ore o giorni per il completamento. Tale tipo di comportamento viene fornito con la necessità di poter controllare lo stato di un'orchestrazione in esecuzione, termina preventivamente o inviare notifiche di eventi esterni.

Per questi casi, l'estensione funzioni permanenti fornisce il `DurableOrchestrationClient` orchestrati di classe che consente di interagire con le funzioni. Puoi accedere al client di orchestrazione utilizzando la `OrchestrationClientAttribute` associazione. In generale, è necessario includere questo attributo con un altro tipo di trigger, ad esempio un `HttpTrigger` o `ServiceBusTrigger`. Dopo che è stata attivata la funzione di origine, il client di orchestrazione è utilizzabile per avviare una funzione di orchestrazione.

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

### <a name="the-orchestrator-function"></a>La funzione di orchestrazione

Annotare una funzione con OrchestrationTriggerAttribute marchi di funzioni di Azure di tale funzione come una funzione di orchestrazione. È responsabile della gestione di varie attività che costituiscono il flusso di lavoro con stato.

Le funzioni di orchestrazione sono in grado di rendere utilizzare diversa da quella di OrchestrationTriggerAttribute. Questo attributo utilizzabile solo con un tipo di parametro di DurableOrchestrationContext. Nessun altro input può essere utilizzato perché non è supportata la deserializzazione dell'input nella firma della funzione. Per ottenere input fornito dal client di orchestrazione, il GetInput\<T\> necessario usare il metodo.

Inoltre, i tipi restituiti delle funzioni di orchestrazione devono essere void, Task o valore JSON serializzabile.

> *La gestione del codice di errore è stato tralasciato, per motivi di brevità*

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

Più istanze di un'orchestrazione possono essere avviato e in esecuzione nello stesso momento. Chiama il `StartNewAsync` metodo sul `DurableOrchestrationClient` avvia una nuova istanza dell'orchestrazione. Il metodo restituisce un `Task<string>` che viene completato quando l'orchestrazione è stata avviata. Un'eccezione di tipo `TimeoutException` Ottiene generata se l'orchestrazione non è ancora stato avviato entro 30 secondi.

Completate `Task<string>` da `StartNewAsync` deve contenere l'ID univoco dell'istanza di orchestrazione. Questo ID istanza è utilizzabile per richiamare le operazioni nell'orchestrazione specifica. L'orchestrazione è possibile eseguire una query per lo stato o inviare le notifiche degli eventi.

### <a name="the-activity-functions"></a>Le funzioni di attività

Funzioni di attività sono le operazioni discrete che vengono composte insieme all'interno di una funzione di orchestrazione per creare il flusso di lavoro. Ecco dove la maggior parte del lavoro effettivo potrebbe essere applicata. Che rappresentano la logica di business, lungo i processi in esecuzione e un puzzle di una soluzione più ampia.

Il `ActivityTriggerAttribute` viene utilizzato per annotare un parametro della funzione di tipo `DurableActivityContext`. Mediante l'annotazione informa il runtime che la funzione deve essere utilizzato come funzione di attività. I valori di input per le funzioni di attività vengono recuperati usando la `GetInput<T>` metodo del `DurableActivityContext` parametro.

Analogamente alle funzioni di orchestrazione, i tipi restituiti di funzioni di attività devono essere void, Task o valore JSON serializzabile.

Eccezioni non gestite generate all'interno di funzioni di attività otterrà inviate alla funzione dell'agente di orchestrazione chiamante e presentate come una `TaskFailedException`. A questo punto, l'errore può essere rilevato e registrato nell'agente di orchestrazione e l'attività è possibile ritentare.

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

* [Funzioni permanenti](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
* [Associazioni per funzioni permanenti](https://docs.microsoft.com/azure/azure-functions/durable-functions-bindings)
* [Gestire le istanze in funzioni permanenti](https://docs.microsoft.com/azure/azure-functions/durable-functions-instance-management)

>[!div class="step-by-step"]
[Precedente](event-grid.md)
[Successivo](orchestration-patterns.md)