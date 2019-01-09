---
title: Griglia di eventi di Azure - App senza server
description: Griglia di eventi di Azure è una soluzione senza server per il recapito di eventi affidabile e il routing su larga scala su un modello di pagamento per evento.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: a10fc6a47322de5db40870b1b727edc5559a27f6
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145884"
---
# <a name="event-grid"></a>Griglia di eventi

[Griglia di eventi di Azure](/azure/event-grid/overview) fornisce infrastruttura senza server per le applicazioni basate su eventi. È possibile pubblicare in griglia di eventi da qualsiasi origine e utilizzare i messaggi da qualsiasi piattaforma. Griglia di eventi offre inoltre supporto incorporato per gli eventi dalle risorse di Azure per semplificare l'integrazione con le applicazioni. Ad esempio, è possibile sottoscrivere gli eventi di archiviazione blob per inviare notifiche all'app quando viene caricato un file. L'applicazione può quindi pubblica un messaggio di griglia di eventi personalizzati che verrà utilizzato da altri cloud o applicazioni in locale. Griglia di eventi è stata progettata per gestire in modo affidabile su larga scala. Si ottengono i vantaggi di pubblicazione e sottoscrizione a messaggi senza l'overhead della configurazione dell'infrastruttura necessaria.

![Logo di griglia di eventi](./media/event-grid-logo.png)

Le funzionalità principali di griglia di eventi includono:

* Routing di eventi completamente gestito.
* In prossimità di recapito di eventi in tempo reale su larga scala.
* Ampia copertura all'interno e all'esterno di Azure.

## <a name="scenarios"></a>Scenari

Griglia di eventi risolve numerosi scenari diversi. Questa sezione illustra tre dei più comuni.

### <a name="ops-automation"></a>Automazione delle operazioni

![Automazione delle operazioni](./media/ops-automation.png)

Griglia di eventi consentono di automazione velocità e semplificare l'applicazione dei criteri notificando [automazione di Azure](https://docs.microsoft.com/azure/automation) quando viene effettuato il provisioning dell'infrastruttura.

### <a name="application-integration"></a>Integrazione dell'applicazione

![Integrazione dell'applicazione](./media/app-integration.png)

È possibile usare griglia di eventi per connettere l'app ad altri servizi. Usa i protocolli HTTP standard, le app legacy anche possono essere modificate facilmente per pubblicare i messaggi di griglia di eventi. Hook Web sono disponibili per altri servizi e piattaforme per utilizzare i messaggi di griglia di eventi.

### <a name="serverless-apps"></a>App senza server

![App senza server](./media/serverless-apps.png)

Griglia di eventi può attivare funzioni di Azure, App per la logica o codice personalizzato. Dei principali vantaggi dell'uso di griglia di eventi è che usa un' *push* meccanismo per inviare i messaggi quando si verificano eventi. L'architettura di push Usa meno risorse e offre una scalabilità migliore rispetto *polling* meccanismi. Polling deve cercare gli aggiornamenti a intervalli regolari.

## <a name="event-grid-vs-other-azure-messaging-services"></a>Griglia di eventi e altri servizi di messaggistica di Azure

Azure offre diversi servizi di messaggistica, incluse [hub eventi](https://docs.microsoft.com/azure/event-hubs) e [Bus di servizio](https://docs.microsoft.com/azure/service-bus-messaging). Ognuno è progettato per soddisfare un set specifico di casi d'uso. Il diagramma seguente offre una panoramica generale delle differenze tra i servizi.

![Confronto di messaggistica di Azure](./media/azure-messaging-services.png)

Per un confronto approfondito, vedere [confrontare servizi di messaggistica](https://docs.microsoft.com/azure/event-grid/compare-messaging-services).

## <a name="performance-targets"></a>Obiettivi di prestazioni

Garantisce tramite griglia di eventi è possibile sfruttare i vantaggi delle prestazioni seguenti:

* Subsecond latenza end-to-end nel 99 ° percentile.
* disponibilità del 99,99%.
* 10 milioni di eventi al secondo per ogni area.
* 100 milioni di sottoscrizioni per ogni area.
* latenza di 50 ms server di pubblicazione.
* 24 ore di ripetizione dei tentativi con backoff esponenziale per il recapito garantito nella finestra di 1 giorno.
* Failover regionale trasparente.

## <a name="event-grid-schema"></a>Schema di griglia di eventi

Griglia di eventi usa uno schema standard per eseguire il wrapping di eventi personalizzati. Lo schema è simile a una busta che esegue il wrapping dell'elemento di dati personalizzati. Ecco un esempio di messaggio di griglia di eventi:

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

Tutto ciò che riguarda il messaggio è standard, ad eccezione di `data` proprietà. È possibile controllare il messaggio e usare la `eventType` e `dataVersion` può essere deserializzata la parte del payload personalizzata.

## <a name="azure-resources"></a>risorse di Azure

Dei principali vantaggi dell'uso di griglia di eventi è gli automatica messaggi prodotti da Azure. In Azure, le risorse automaticamente pubblicano in un *argomento* che consente di sottoscrivere i vari eventi. La tabella seguente elenca i tipi di risorse, i tipi di messaggio e gli eventi che sono disponibili automaticamente.

| Risorse di Azure | Tipo evento | Descrizione |
| -------------- | ---------- | ----------- |
| Sottoscrizione di Azure | Microsoft.Resources.ResourceWriteSuccess | Generato quando una risorsa di creazione o l'operazione di aggiornamento ha esito positivo. |
| | Microsoft.Resources.ResourceWriteFailure | Generato quando si crea una risorsa o l'operazione di aggiornamento ha esito negativo. |
| | Microsoft.Resources.ResourceWriteCancel | Generato quando una risorsa di creazione o l'operazione di aggiornamento viene annullata. |
|  | Microsoft.Resources.ResourceDeleteSuccess | Generato quando un'operazione di eliminazione della risorsa ha esito positivo. |
|  | Microsoft.Resources.ResourceDeleteFailure | Generato quando un'operazione di eliminazione della risorsa ha esito negativo. |
| | Resourcedeletecancel | Generato quando viene annullata un'operazione di eliminazione di risorse. Questo evento si verifica quando viene annullata una distribuzione modello. |
| Archiviazione BLOB | Microsoft.Storage.BlobCreated | Generato quando viene creato un blob. |
| | Microsoft.Storage.BlobDeleted | Generato quando viene eliminato un blob. |
| Hub eventi | Microsoft.EventHub.CaptureFileCreated | Generato quando viene creato un file di acquisizione.
| Hub IoT | Microsoft.Devices.DeviceCreated | Pubblicato quando un dispositivo viene registrato a un hub IoT. |
| | Microsoft.Devices.DeviceDeleted | Pubblicato quando un dispositivo viene eliminato da un hub IoT. |
| Gruppi di risorse | Microsoft.Resources.ResourceWriteSuccess | Generato quando una risorsa di creazione o l'operazione di aggiornamento ha esito positivo. |
| | Microsoft.Resources.ResourceWriteFailure | Generato quando si crea una risorsa o l'operazione di aggiornamento ha esito negativo. |
| | Microsoft.Resources.ResourceWriteCancel | Generato quando una risorsa di creazione o l'operazione di aggiornamento viene annullata. |
| | Microsoft.Resources.ResourceDeleteSuccess | Generato quando un'operazione di eliminazione della risorsa ha esito positivo. |
| | Microsoft.Resources.ResourceDeleteFailure | Generato quando un'operazione di eliminazione della risorsa ha esito negativo. |
| | Resourcedeletecancel | Generato quando viene annullata un'operazione di eliminazione di risorse. Questo evento si verifica quando viene annullata una distribuzione modello. |

Per altre informazioni, vedere [schema di eventi di griglia di eventi di Azure](https://docs.microsoft.com/azure/event-grid/event-schema).

Griglia di eventi è possibile accedere da qualsiasi tipo di applicazione, anche se non viene eseguito in locale.

## <a name="conclusion"></a>Conclusione

In questo capitolo si è appreso sulla piattaforma Azure senza server che è costituita da funzioni di Azure, App per la logica e griglia di eventi. È possibile usare queste risorse per compilare un'architettura di app senza server completamente o creare una soluzione ibrida che interagisce con altre risorse cloud e nei server locali. Combinata con una piattaforma di dati senza server, ad esempio [SQL di Azure](https://docs.microsoft.com/azure/sql-database) oppure [CosmosDB](https://docs.microsoft.com/azure/cosmos-db/introduction), è possibile compilare applicazioni native cloud completamente gestito.

## <a name="recommended-resources"></a>Risorse consigliate

* [Piani di servizio App](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)
* [Application Insights](https://docs.microsoft.com/azure/application-insights)
* [Application Insights Analitica](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)
* [Azure: Crea la tua app nel cloud con funzioni di Azure senza server](https://channel9.msdn.com/events/Connect/2017/E102)
* [Griglia di eventi di Azure](https://docs.microsoft.com/azure/azure-event-grid/overview)
* [Schema di eventi di griglia di eventi Azure](https://docs.microsoft.com/azure/event-grid/event-schema)
* [Hub eventi di Azure](https://docs.microsoft.com/azure/event-hubs)
* [Documentazione di funzioni di Azure](https://docs.microsoft.com/azure/azure-functions)
* [Concetti di binding e trigger delle funzioni di Azure](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)
* [App per la logica di Azure](https://docs.microsoft.com/azure/logic-apps)
* [Bus di servizio di Azure](https://docs.microsoft.com/azure/service-bus-messaging)
* [Archiviazione tabelle di Azure](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview)
* [Confrontare funzioni 1.x e 2.x](https://docs.microsoft.com/azure/azure-functions/functions-versions)
* [La connessione a origini dati locali con Azure sul Gateway dati locale](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway)
* [Creare la prima funzione nel portale di Azure](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)
* [Creare la prima funzione usando il comando di Azure](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)
* [Creare la prima funzione con Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio)
* [Lingue supportate le funzioni](https://docs.microsoft.com/azure/azure-functions/supported-languages)
* [Monitorare funzioni di Azure](https://docs.microsoft.com/azure/azure-functions/functions-monitoring)
* [Lavorare con i proxy di funzioni di Azure](https://docs.microsoft.com/azure/azure-functions/functions-proxies)

>[!div class="step-by-step"]
>[Precedente](logic-apps.md)
>[Successivo](durable-azure-functions.md)
