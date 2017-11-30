---
title: Implementazione di comunicazione tra microservizi (eventi di integrazione) basata su eventi
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Implementazione di comunicazione tra microservizi (eventi di integrazione) basata su eventi
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: e438607ab3549d63b89bef6af64c6723a4cac950
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-event-based-communication-between-microservices-integration-events"></a>Implementazione di comunicazione tra microservizi (eventi di integrazione) basata su eventi

Come descritto in precedenza, quando si usa la comunicazione basata su eventi, un microservizio pubblica un evento quando rilevanti, ad esempio quando aggiorna un'entità di business. Altri microservizi sottoscrivono tali eventi. Quando un microservizio riceve un evento, è possibile aggiornare il proprio entità aziendali, che è possibile che si verifichino più eventi in corso di pubblicazione. Questo sistema di pubblicazione/sottoscrizione viene in genere eseguito tramite un'implementazione di un bus di eventi. Il bus di eventi può essere progettato come un'interfaccia con l'API necessaria per sottoscrivere e annullare la sottoscrizione a eventi e per pubblicare eventi. Può anche avere uno o più implementazioni in base a qualsiasi comunicazione tra processi o messaggistica, ad esempio una coda di messaggi o di un bus di servizio che supporta la comunicazione asincrona e un modello di pubblicazione/sottoscrizione.

È possibile utilizzare gli eventi per implementare le transazioni di business che si estendono su più servizi, che offre la coerenza eventuale tra tali servizi. Una transazione alla fine coerente è costituito da una serie di azioni distribuite. In ogni azione, il microservizio aggiorna un'entità di business e pubblica un evento che attiva l'azione successiva.

![](./media/image19.PNG)

**Figura 8-18**. Comunicazione basata sugli eventi in base a un bus di eventi

Questa sezione descrive come è possibile implementare questo tipo di comunicazione con .NET tramite un'interfaccia di bus di eventi generici, come illustrato nella figura 8-18. Sono disponibili più implementazioni di potenziali, ognuno dei quali utilizza una tecnologia diversa o dell'infrastruttura, ad esempio RabbitMQ, Azure Service Bus, qualsiasi altro open source di terze parti o bus di servizio esterno.

## <a name="using-message-brokers-and-services-buses-for-production-systems"></a>Tramite il bus di servizi e i gestori di messaggi per i sistemi di produzione

Come indicato nella sezione architettura, è possibile scegliere tra più tecnologie di messaggistica per l'implementazione del bus di eventi astratti. Ma queste tecnologie sono a livelli diversi. RabbitMQ, un trasporto di Service broker di messaggistica, ad esempio, è un livello inferiore rispetto a come Azure Service Bus, NServiceBus, MassTransit o Brighter prodotti. La maggior parte di questi prodotti possono lavorare su RabbitMQ o Azure Service Bus. La scelta del prodotto dipende il numero di funzionalità e la scalabilità quanto out-of-the-box è necessario per l'applicazione.

Per implementare solo un evento bus di prova per l'ambiente di sviluppo, come nell'esempio eShopOnContainers, un'implementazione semplice sopra RabbitMQ in esecuzione come un contenitore potrebbe essere sufficiente. Ma per mission-critical e sistemi di produzione che richiedono scalabilità elevata, può essere opportuno valutare e utilizzare Azure Service Fabric. Se è necessario astrazioni di alto livello e le funzionalità più dettagliate come [sagas](https://docs.particular.net/nservicebus/sagas/) per processi a esecuzione prolungata che consentono uno sviluppo distribuito bus più semplice e altri servizi commerciali e open-source come NServiceBus, MassTransit, e Sono più opportuno valutare. Naturalmente, è sempre possibile creare funzionalità personalizzate bus di servizio su tecnologie di livello inferiore come RabbitMQ e Docker, ma il lavoro necessario per rifare potrebbe essere troppo costoso per un'applicazione personalizzati dell'organizzazione.

Per riepilogare: l'astrazioni di bus di eventi campione e l'implementazione mostrata nell'esempio di eShopOnContainers deve essere utilizzato solo come un modello di prova. Dopo aver scelto che si desidera la comunicazione asincrona e basata sugli eventi, come illustrato nella sezione corrente, è necessario scegliere il prodotto di bus di servizio che meglio si adatta alle esigenze.

## <a name="integration-events"></a>Eventi di integrazione

Eventi di integrazione vengono utilizzati per riportare lo stato di dominio di sincronizzazione tra più microservizi o sistemi esterni. Questa operazione viene eseguita tramite la pubblicazione di eventi di integrazione di fuori di microservizio. Quando un evento viene pubblicato in più microservizi ricevitore (per tante microservizi come sottoscritto l'evento di integrazione), il gestore eventi appropriato in ogni microservizio ricevitore gestisce l'evento.

Un evento di integrazione è sostanzialmente una classe che contiene di dati, come nell'esempio seguente:

```csharp
public class ProductPriceChangedIntegrationEvent : IntegrationEvent
{
    public int ProductId { get; private set; }
    public decimal NewPrice { get; private set; }
    public decimal OldPrice { get; private set; }

    public ProductPriceChangedIntegrationEvent(int productId, decimal newPrice,
        decimal oldPrice)
    {
        ProductId = productId;
        NewPrice = newPrice;
        OldPrice = oldPrice;
    }
}
```

La classe di evento di integrazione può essere semplice. ad esempio, potrebbe contenere un GUID per il relativo ID.

Gli eventi di integrazione possono essere definiti a livello di applicazione di ogni microservizio, in modo che vengono disaccoppiati da altri microservizi, in modo analogo a come ViewModel sono definiti nel server e client. Che cos'è consigliabile non condivide una libreria di eventi di integrazione comuni tra più microservizi; Questa operazione potrebbe essere accoppiamento tra tali microservizi con una raccolta di dati singolo evento definizione. Non si desidera eseguire questa operazione per gli stessi motivi non si desidera condividere un comune modello di dominio più microservizi: microservizi devono essere completamente autonomo.

Esistono solo alcuni tipi di librerie, che è necessario condividere microservizi. Uno è librerie di blocchi dell'applicazione finale, ad esempio il [API client di Bus di eventi](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/BuildingBlocks/EventBus), come nel eShopOnContainers. Un vantaggio è librerie che costituiscono gli strumenti che può essere condivisa anche come componenti di NuGet, come i serializzatori JSON.

## <a name="the-event-bus"></a>Il bus di eventi

Un bus di eventi consente la comunicazione di pubblicazione/sottoscrizione-stile tra microservizi senza i componenti in modo esplicito essere a conoscenza della loro, come illustrato nella figura 8-19.

![](./media/image20.png)

**Figura 8-19**. Nozioni di base con un bus di eventi di pubblicazione/sottoscrizione

Il bus di eventi è correlato all'Observer (modello) e la pubblicazione-modello di sottoscrizione.

### <a name="observer-pattern"></a>Observer (modello)

Nel [osservatore](https://en.wikipedia.org/wiki/Observer_pattern), l'oggetto primario (noto come Observable) notifica agli altri oggetti interessati (noti come osservatori) con le informazioni pertinenti (eventi).

### <a name="publish-subscribe-pubsub-pattern"></a>Modello pubblicazione-sottoscrizione (Pub/Sub) 

Lo scopo del [modello Pub/Sub](https://msdn.microsoft.com/en-us/library/ff649664.aspx) corrisponde al modello di osservatore: si desidera notificare agli altri servizi quando si verificano determinati eventi. Ma non esiste una differenza importante semantica tra i modelli di osservatore e pubblicazione/sottoscrizione. Nel modello di pubblicazione/sottoscrizione, è attiva la diffusione messaggi. Al contrario, nel modello Observer, Observable non riconosce che gli eventi verranno, solo che che sono state registrate out. In altre parole, Observable (server di pubblicazione) non riconosce che gli osservatori (sottoscrittori).

### <a name="the-middleman-or-event-bus"></a>Il bus di eventi o di intermediario 

Come è possibile ottenere anonimato tra server di pubblicazione e sottoscrittore? Un modo semplice è fare in modo che un intermediario di tutte le comunicazioni. Un bus di eventi è un intermediario di questo tipo.

Un bus di eventi è in genere costituito da due parti:

-   Astrazione o interfaccia.

-   Uno o più implementazioni.

Nella figura 8-19 è possibile visualizzare, dal punto di vista dell'applicazione, il bus di eventi è di un canale di pubblicazione/sottoscrizione. La modalità di implementazione di questa comunicazione asincrona può variare. Ciò può avere più implementazioni in modo che sia possibile passare tra di esse, a seconda dei requisiti di ambiente (ad esempio, di produzione e gli ambienti di sviluppo).

Nella figura 8-20 è possibile visualizzare un'astrazione di un bus di eventi con più implementazioni in base all'infrastruttura di messaggistica di tecnologie quali RabbitMQ, Bus di servizio di Azure o altri bus di servizio NServiceBus, MassTransit, ecc.

![](./media/image21.png)

**Figura 8 - 20.** Più implementazioni del bus di eventi

Tuttavia, come evidenziato in precedenza, mediante astrazioni (l'interfaccia di bus di eventi) è possibile solo se sono necessarie funzionalità di bus di eventi di base supportate dalle astrazioni. Se è necessario maggiori funzionalità di bus di servizio, utilizzare probabilmente all'API fornita da del bus di servizio preferito anziché la propria astrazioni.

### <a name="defining-an-event-bus-interface"></a>Definizione di un'interfaccia di bus di eventi

Iniziamo con un codice di implementazione per l'interfaccia del bus di eventi e le implementazioni possibili per scopi di esplorazione. L'interfaccia deve essere generico e semplice, come l'interfaccia seguente.

```csharp
public interface IEventBus
{
    void Publish(IntegrationEvent @event);
    void Subscribe<T>(IIntegrationEventHandler<T> handler)
        where T: IntegrationEvent;

    void Unsubscribe<T>(IIntegrationEventHandler<T> handler)
        where T : IntegrationEvent;
}
```

Il metodo di pubblicazione è semplice. Il bus di eventi verrà trasmesso l'evento di integrazione passato a qualsiasi microservizio sottoscritta l'evento. Questo metodo viene utilizzato da microservizio che pubblica l'evento.

Viene utilizzato il metodo di sottoscrizione da microservizi che desidera ricevere gli eventi. Questo metodo è costituito da due parti. Il primo è l'evento di integrazione per la sottoscrizione (IntegrationEvent). La seconda parte è il gestore di eventi di integrazione (o metodo di callback) da chiamare (IIntegrationEventHandler&lt;T&gt;) quando il microservizio riceve il messaggio di evento di integrazione.


>[!div class="step-by-step"]
[Precedente] (container.md-server-database) [Avanti] (rabbitmq-event-bus-development-test-environment.md)
