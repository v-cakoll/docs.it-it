---
title: Griglia di eventi di Azure - App senza serverAzure Event Grid - Serverless apps
description: Griglia di eventi di Azure è una soluzione senza server per il recapito e il routing di eventi affidabili su larga scala in un modello a pagamento per evento.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 3c577139c12567e762aabd58c9dc29457fa37aa1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522710"
---
# <a name="event-grid"></a>Griglia di eventi

[Griglia di eventi](/azure/event-grid/overview) di Azure offre un'infrastruttura senza server per le applicazioni basate su eventi. È possibile pubblicare in Griglia di eventi da qualsiasi origine e utilizzare i messaggi da qualsiasi piattaforma. Griglia di eventi include anche il supporto incorporato per gli eventi dalle risorse di Azure per semplificare l'integrazione con le applicazioni. Ad esempio, è possibile sottoscrivere gli eventi di archiviazione BLOB per notificare all'app quando viene caricato un file. L'applicazione può quindi pubblicare un messaggio della griglia di eventi personalizzato utilizzato da altre applicazioni cloud o locali. Event Grid è stato costruito per gestire in modo affidabile la scala massiccia. È possibile ottenere i vantaggi della pubblicazione e dell'iscrizione ai messaggi senza il sovraccarico di configurare l'infrastruttura necessaria.

![Logo della griglia di eventi](./media/event-grid-logo.png)

Le principali caratteristiche della griglia degli eventi includono:

- Routing degli eventi completamente gestito.
- Recapito quasi in tempo reale degli eventi su larga scala.
- Ampia copertura sia all'interno che all'esterno di Azure.

## <a name="scenarios"></a>Scenari

Griglia di eventi affronta diversi scenari. Questa sezione copre tre dei più comuni.

### <a name="ops-automation"></a>Automazione delle operazioni

![Automazione delle operazioni](./media/ops-automation.png)

Griglia di eventi consente di velocizzare l'automazione e semplificare l'applicazione dei criteri notificando [l'automazione](https://docs.microsoft.com/azure/automation) di Azure quando viene eseguito il provisioning dell'infrastruttura.

### <a name="application-integration"></a>Integrazione di applicazioni

![Integrazione di applicazioni](./media/app-integration.png)

Puoi usare Griglia di eventi per connettere l'app ad altri servizi. Utilizzando i protocolli HTTP standard, anche le app legacy possono essere facilmente modificate per pubblicare i messaggi della griglia di eventi. Gli hook Web sono disponibili per altri servizi e piattaforme per l'utilizzo dei messaggi della griglia di eventi.

### <a name="serverless-apps"></a>App serverless

![App serverless](./media/serverless-apps.png)

Griglia di eventi può attivare Funzioni di Azure, App per la logica o il proprio codice personalizzato. Uno dei principali vantaggi dell'utilizzo di Griglia di eventi è che utilizza un meccanismo *push* per inviare messaggi quando si verificano eventi. L'architettura push utilizza meno risorse e scala meglio rispetto ai meccanismi di *polling.* Il polling deve verificare la disponibilità di aggiornamenti a intervalli regolari.

## <a name="event-grid-vs-other-azure-messaging-services"></a>Griglia di eventi e altri servizi di messaggistica di AzureEvent Grid vs.

Azure fornisce diversi servizi di messaggistica, tra cui [Hub eventi](https://docs.microsoft.com/azure/event-hubs) e Bus [di servizio.](https://docs.microsoft.com/azure/service-bus-messaging) Ciascuno di essi è progettato per affrontare una serie specifica di casi d'uso. Nel diagramma seguente viene fornita una panoramica generale delle differenze tra i servizi.

![Confronto tra messaggistica di AzureAzure messaging comparison](./media/azure-messaging-services.png)

Per un confronto più approfondito, vedere [Confrontare i servizi di messaggistica.](https://docs.microsoft.com/azure/event-grid/compare-messaging-services)

## <a name="performance-targets"></a>Prestazioni richieste

Utilizzando Griglia di eventi è possibile sfruttare le seguenti garanzie di prestazioni:

- Latenza end-to-end del 99esimo percentile.
- Disponibilità del 99.99%.
- 10 milioni di eventi al secondo per regione.
- 100 milioni di abbonamenti per regione.
- Latenza del server di pubblicazione di 50 ms.
- Nuovo tentativo di 24 ore su 24 con back-off esponenziale per la consegna garantita nella finestra di 1 giorno.
- Failover regionale trasparente.

## <a name="event-grid-schema"></a>Schema di Griglia di eventi

Griglia di eventi utilizza uno schema standard per eseguire il wrapping degli eventi personalizzati. Lo schema è simile a una busta che esegue il wrapping dell'elemento dati personalizzato. Di seguito è riportato un messaggio griglia di eventi di esempio:Here is an example Event Grid message:

```json
[{
    "id": "03e24f21-a955-43cc-8921-1f61a6081ce0",
    "eventType": "myCustomEvent",
    "subject": "foo/bar/12",
    "eventTime": "2018-09-22T10:36:01+00:00",
    "data": {
        "favoriteColor": "blue",
        "favoriteAnimal": "panther",
        "favoritePlanet": "Jupiter"
    },
    "dataVersion": "1.0"
}]
```

Tutto ciò che riguarda `data` il messaggio è standard tranne la proprietà. È possibile esaminare il `eventType` `dataVersion` messaggio e utilizzare e deserializzare la parte personalizzata del payload.

## <a name="azure-resources"></a>Risorse di Azure

Uno dei principali vantaggi dell'uso di Griglia di eventi sono i messaggi automatici prodotti da Azure.A major benefit of using Event Grid is the automatic messages produced by Azure. In Azure le risorse vengono pubblicate automaticamente in un *argomento* che consente di sottoscrivere vari eventi. Nella tabella seguente sono elencati i tipi di risorse, i tipi di messaggio e gli eventi disponibili automaticamente.

| Risorsa di Azure | Tipo di evento | Descrizione |
| -------------- | ---------- | ----------- |
| Sottoscrizione di Azure | Microsoft.Resources.ResourceWriteSuccess | Generato quando un'operazione di creazione o aggiornamento di una risorsa ha esito positivo. |
| | Microsoft.Resources.ResourceWriteFailure | Generato quando un'operazione di creazione o aggiornamento di una risorsa ha esito negativo. |
| | Microsoft.Resources.ResourceWriteCancel | Generato quando un'operazione di creazione o aggiornamento di una risorsa viene annullata. |
|  | Microsoft.Resources.ResourceDeleteSuccess | Generato quando un'operazione di eliminazione di una risorsa ha esito positivo. |
|  | Microsoft.Resources.ResourceDeleteFailure | Generato quando un'operazione di eliminazione di una risorsa ha esito negativo. |
| | Microsoft.Resources.ResourceDeleteCancel | Generato quando un'operazione di eliminazione di una risorsa viene annullata. Questo evento si verifica quando viene annullata la distribuzione di un modello. |
| Archiviazione BLOB | Microsoft.Storage.BlobCreated | Generato quando viene creato un BLOB. |
| | Microsoft.Storage.BlobDeleted | Generato quando viene eliminato un BLOB. |
| Hub eventi | Microsoft.EventHub.CaptureFileCreated | Generato quando viene creato un file di acquisizione.
| Hub IoT | Microsoft.Devices.DeviceCreated | Pubblicato quando un dispositivo viene registrato in un hub IoT. |
| | Microsoft.Devices.DeviceDeleted | Pubblicato quando un dispositivo viene eliminato da un hub IoT. |
| Gruppi di risorse | Microsoft.Resources.ResourceWriteSuccess | Generato quando un'operazione di creazione o aggiornamento di una risorsa ha esito positivo. |
| | Microsoft.Resources.ResourceWriteFailure | Generato quando un'operazione di creazione o aggiornamento di una risorsa ha esito negativo. |
| | Microsoft.Resources.ResourceWriteCancel | Generato quando un'operazione di creazione o aggiornamento di una risorsa viene annullata. |
| | Microsoft.Resources.ResourceDeleteSuccess | Generato quando un'operazione di eliminazione di una risorsa ha esito positivo. |
| | Microsoft.Resources.ResourceDeleteFailure | Generato quando un'operazione di eliminazione di una risorsa ha esito negativo. |
| | Microsoft.Resources.ResourceDeleteCancel | Generato quando un'operazione di eliminazione di una risorsa viene annullata. Questo evento si verifica quando viene annullata la distribuzione di un modello. |

Per altre informazioni, vedere [Schema di eventi Griglia di eventi](https://docs.microsoft.com/azure/event-grid/event-schema)di Azure.For more information, see Azure Event Grid event schema .

È possibile accedere a Griglia di eventi da qualsiasi tipo di applicazione, anche in locale.

## <a name="conclusion"></a>Conclusioni

In questo capitolo si è appresa la piattaforma senza server di Azure composta da Funzioni di Azure, App per la logica e Griglia di eventi. È possibile usare queste risorse per creare un'architettura di app completamente senza server o creare una soluzione ibrida che interagisce con altre risorse cloud e server locali. In combinazione con una piattaforma dati senza server, ad esempio SQL di [Azure](https://docs.microsoft.com/azure/sql-database) o [CosmosDB](https://docs.microsoft.com/azure/cosmos-db/introduction), è possibile creare applicazioni native cloud completamente gestite.

## <a name="recommended-resources"></a>Risorse consigliate

- [Piani di servizio app](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)
- [Application Insights](https://docs.microsoft.com/azure/application-insights)
- [Analytics in Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)
- [Azure: Bring your app to the cloud with serverless Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102)
- [Griglia di eventi di AzureAzure Event Grid](https://docs.microsoft.com/azure/event-grid/overview)
- [Schema di eventi di Griglia di eventi di Azure](https://docs.microsoft.com/azure/event-grid/event-schema)
- [Hub eventi di Azure](https://docs.microsoft.com/azure/event-hubs)
- [Documentazione di Funzioni di AzureAzure Functions documentation](https://docs.microsoft.com/azure/azure-functions)
- [Concetti relativi a trigger e associazioni in Funzioni di Azure](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)
- [App per la logica di AzureAzure Logic Apps](https://docs.microsoft.com/azure/logic-apps)
- [Bus di servizio di AzureAzure Service Bus](https://docs.microsoft.com/azure/service-bus-messaging)
- [Archiviazione tabelle di AzureAzure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview)
- [Confrontare le funzioni 1.x e 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions)
- [Connessione a origini dati locali con gateway dati locale di Azure](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway)
- [Creare la prima funzione nel portale di Azure](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)
- [Creare la prima funzione usando l'interfaccia della riga di comando di Azure](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)
- [Creare la prima funzione con Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio)
- [Lingue supportate da funzioni](https://docs.microsoft.com/azure/azure-functions/supported-languages)
- [Monitorare Funzioni di Azure](https://docs.microsoft.com/azure/azure-functions/functions-monitoring)
- [Usare i proxy di Funzioni di Azure](https://docs.microsoft.com/azure/azure-functions/functions-proxies)

>[!div class="step-by-step"]
>[Successivo](logic-apps.md)
>[precedente](durable-azure-functions.md)
