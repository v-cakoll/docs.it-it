---
title: Griglia di eventi di Azure-app senza server
description: Griglia di eventi di Azure è una soluzione senza server per il recapito di eventi affidabili e il routing su larga scala su un modello con pagamento per evento.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 04/06/2020
ms.openlocfilehash: 408e1b9cd1b1e5316c7c6a17bb1b0c76a38f9e11
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135711"
---
# <a name="event-grid"></a>Griglia di eventi

[Griglia di eventi di Azure](/azure/event-grid/overview) offre un'infrastruttura senza server per le applicazioni basate su eventi. È possibile pubblicare in griglia di eventi da qualsiasi origine e utilizzare i messaggi di qualsiasi piattaforma. Griglia di eventi include anche il supporto integrato per gli eventi delle risorse di Azure per semplificare l'integrazione con le applicazioni. Ad esempio, è possibile sottoscrivere gli eventi di archiviazione BLOB per inviare una notifica all'app quando viene caricato un file. L'applicazione può quindi pubblicare un messaggio di griglia di eventi personalizzato che viene utilizzato da altre applicazioni cloud o locali. Griglia di eventi è stata creata per gestire in modo affidabile un'ampia scalabilità. Si ottengono i vantaggi della pubblicazione e della sottoscrizione ai messaggi senza l'overhead della configurazione dell'infrastruttura necessaria.

![Logo di griglia di eventi](./media/event-grid-logo.png)

Le funzionalità principali di griglia di eventi includono:

- Routing di eventi completamente gestito.
- Recapito di eventi quasi in tempo reale su larga scala.
- Ampia copertura sia all'interno che all'esterno di Azure.

## <a name="scenarios"></a>Scenari

Griglia di eventi affronta diversi scenari diversi. Questa sezione descrive tre dei più comuni.

### <a name="ops-automation"></a>Automazione delle operazioni

![Automazione delle operazioni](./media/ops-automation.png)

Griglia di eventi consente di velocizzare l'automazione e semplificare l'applicazione dei criteri inviando una notifica ad [automazione di Azure](https://docs.microsoft.com/azure/automation) quando viene effettuato il provisioning dell'infrastruttura.

### <a name="application-integration"></a>Integrazione di applicazioni

![Integrazione di applicazioni](./media/app-integration.png)

È possibile usare griglia di eventi per connettere l'app ad altri servizi. Usando i protocolli HTTP standard, anche le app legacy possono essere facilmente modificate per pubblicare i messaggi della griglia di eventi. Gli hook Web sono disponibili per altri servizi e piattaforme per l'utilizzo di messaggi di griglia di eventi.

### <a name="serverless-apps"></a>App serverless

![App serverless](./media/serverless-apps.png)

Griglia di eventi può attivare funzioni di Azure, app per la logica o codice personalizzato. Un importante vantaggio dell'uso di griglia di eventi è che usa un meccanismo di *push* per inviare messaggi quando si verificano eventi. L'architettura Push utilizza un minor numero di risorse e scalabilità migliore rispetto ai meccanismi di *polling* . Il polling deve verificare la disponibilità di aggiornamenti a intervalli regolari.

## <a name="event-grid-vs-other-azure-messaging-services"></a>Griglia di eventi rispetto ad altri servizi di messaggistica di Azure

Azure offre diversi servizi di messaggistica, tra cui [Hub eventi](https://docs.microsoft.com/azure/event-hubs) e [bus di servizio](https://docs.microsoft.com/azure/service-bus-messaging). Ogni è progettato per risolvere un set specifico di casi d'uso. Il diagramma seguente fornisce una panoramica di alto livello delle differenze tra i servizi.

![Confronto tra messaggistica di Azure](./media/azure-messaging-services.png)

Per un confronto più dettagliato, vedere confrontare i [servizi di messaggistica](https://docs.microsoft.com/azure/event-grid/compare-messaging-services).

## <a name="performance-targets"></a>Prestazioni richieste

Utilizzando griglia di eventi è possibile sfruttare le garanzie di prestazioni seguenti:

- Latenza end-to-end secondaria nel 99 ° percentile.
- Disponibilità del 99.99%.
- 10 milioni eventi al secondo per area.
- 100 milioni sottoscrizioni per area.
- 50-latenza autore ms.
- tentativo di 24 ore con il back-off esponenziale per il recapito garantito nella finestra di un giorno.
- Failover a livello di area trasparente.

## <a name="event-grid-schema"></a>Schema di Griglia di eventi

Griglia di eventi usa uno schema standard per eseguire il wrapping degli eventi personalizzati. Lo schema è simile a una busta che esegue il wrapping dell'elemento dati personalizzato. Di seguito è riportato un esempio di messaggio di griglia di eventi:

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

Tutte le informazioni sul messaggio sono standard, `data` ad eccezione della proprietà. È possibile esaminare il messaggio e utilizzare `eventType` e `dataVersion` per deserializzare la porzione personalizzata del payload.

## <a name="azure-resources"></a>Risorse di Azure

Un vantaggio principale dell'uso di griglia di eventi è costituito dai messaggi automatici prodotti da Azure. In Azure le risorse vengono pubblicate automaticamente in un *argomento* che consente di effettuare la sottoscrizione per diversi eventi. Nella tabella seguente sono elencati i tipi di risorse, i tipi di messaggi e gli eventi disponibili automaticamente.

| Risorsa di Azure | Tipo di evento | Description |
| -------------- | ---------- | ----------- |
| Sottoscrizione di Azure | Microsoft.Resources.ResourceWriteSuccess | Generato quando un'operazione di creazione o aggiornamento di una risorsa ha esito positivo. |
| | Microsoft.Resources.ResourceWriteFailure | Generato quando un'operazione di creazione o aggiornamento di una risorsa ha esito negativo. |
| | Microsoft.Resources.ResourceWriteCancel | Generato quando un'operazione di creazione o aggiornamento di una risorsa viene annullata. |
|  | Microsoft.Resources.ResourceDeleteSuccess | Generato quando un'operazione di eliminazione di una risorsa ha esito positivo. |
|  | Microsoft.Resources.ResourceDeleteFailure | Generato quando un'operazione di eliminazione di una risorsa ha esito negativo. |
| | Microsoft.Resources.ResourceDeleteCancel | Generato quando un'operazione di eliminazione di una risorsa viene annullata. Questo evento si verifica quando viene annullata la distribuzione di un modello. |
| Archiviazione BLOB | Microsoft.Storage.BlobCreated | Generato quando viene creato un BLOB. |
| | Microsoft.Storage.BlobDeleted | Generato quando viene eliminato un BLOB. |
| Hub eventi | Microsoft. EventHub. CaptureFileCreated | Generato quando viene creato un file di acquisizione.
| Hub IoT | Microsoft.Devices.DeviceCreated | Pubblicato quando un dispositivo viene registrato in un hub IoT. |
| | Microsoft.Devices.DeviceDeleted | Pubblicato quando un dispositivo viene eliminato da un hub IoT. |
| Gruppi di risorse | Microsoft.Resources.ResourceWriteSuccess | Generato quando un'operazione di creazione o aggiornamento di una risorsa ha esito positivo. |
| | Microsoft.Resources.ResourceWriteFailure | Generato quando un'operazione di creazione o aggiornamento di una risorsa ha esito negativo. |
| | Microsoft.Resources.ResourceWriteCancel | Generato quando un'operazione di creazione o aggiornamento di una risorsa viene annullata. |
| | Microsoft.Resources.ResourceDeleteSuccess | Generato quando un'operazione di eliminazione di una risorsa ha esito positivo. |
| | Microsoft.Resources.ResourceDeleteFailure | Generato quando un'operazione di eliminazione di una risorsa ha esito negativo. |
| | Microsoft.Resources.ResourceDeleteCancel | Generato quando un'operazione di eliminazione di una risorsa viene annullata. Questo evento si verifica quando viene annullata la distribuzione di un modello. |

Per altre informazioni, vedere [schema di eventi di griglia di eventi di Azure](https://docs.microsoft.com/azure/event-grid/event-schema).

È possibile accedere a griglia di eventi da qualsiasi tipo di applicazione, anche se eseguita in locale.

## <a name="conclusion"></a>Conclusioni

In questo capitolo sono state illustrate le informazioni sulla piattaforma senza server di Azure composta da funzioni di Azure, app per la logica e griglia di eventi. È possibile usare queste risorse per creare un'architettura di app interamente senza server oppure creare una soluzione ibrida che interagisce con altre risorse cloud e server locali. In combinazione con una piattaforma dati senza server come [Azure SQL](https://docs.microsoft.com/azure/sql-database) o [CosmosDB](https://docs.microsoft.com/azure/cosmos-db/introduction), è possibile creare applicazioni native cloud completamente gestite.

## <a name="recommended-resources"></a>Risorse consigliate

- [Piani di servizio app](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)
- [Application Insights](https://docs.microsoft.com/azure/application-insights)
- [Analytics in Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)
- [Azure: porta la tua app nel cloud con funzioni di Azure senza server](https://channel9.msdn.com/events/Connect/2017/E102)
- [Griglia di eventi di Azure](https://docs.microsoft.com/azure/event-grid/overview)
- [Schema di eventi di Griglia di eventi di Azure](https://docs.microsoft.com/azure/event-grid/event-schema)
- [Hub eventi di Azure](https://docs.microsoft.com/azure/event-hubs)
- [Documentazione di Funzioni di Azure](https://docs.microsoft.com/azure/azure-functions)
- [Concetti relativi a trigger e associazioni in Funzioni di Azure](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)
- [App per la logica di Azure](https://docs.microsoft.com/azure/logic-apps)
- [Bus di servizio di Azure](https://docs.microsoft.com/azure/service-bus-messaging)
- [Archiviazione tabelle di Azure](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview)
- [Connessione a origini dati locali con gateway dati locale di Azure](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway)
- [Creare la prima funzione nel portale di Azure](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)
- [Creare la prima funzione usando l'interfaccia della riga di comando di Azure](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)
- [Creare la prima funzione con Visual Studio](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio)
- [Lingue supportate dalle funzioni](https://docs.microsoft.com/azure/azure-functions/supported-languages)
- [Monitorare Funzioni di Azure](https://docs.microsoft.com/azure/azure-functions/functions-monitoring)

>[!div class="step-by-step"]
>[Precedente](logic-apps.md)
>[successivo](durable-azure-functions.md)
