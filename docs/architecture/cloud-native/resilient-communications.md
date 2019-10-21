---
title: Comunicazione resiliente
description: Architettura di app .NET cloud native per Azure | Comunicazione resiliente
ms.date: 06/30/2019
ms.openlocfilehash: 324f5426af1c892db73aa6fc2336a19b7a8e499e
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72315806"
---
# <a name="resilient-communications"></a>Comunicazioni resilienti

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

In questo libro abbiamo evangelizzato i meriti del passaggio oltre la tradizionale progettazione di applicazioni monolitiche e l'adozione di un'architettura basata su microservizi in cui un set di servizi distribuiti e indipendenti viene eseguito in modo indipendente e comunica con ognuno altro con protocolli di comunicazione standard, ad esempio HTTP e HTTPS. Sebbene tale architettura acquisti molti vantaggi importanti, presenta anche molti problemi. Si considerino, ad esempio, i seguenti aspetti:

- *Comunicazione di rete out-of-process.* Ogni servizio comunica tramite un protocollo di rete che introduce congestioni di rete, latenza ed errori temporanei.
- *Individuazione del servizio.* Con ogni servizio in esecuzione in un cluster di computer con il proprio indirizzo IP e la propria porta, in che modo i servizi individuano e comunicano tra loro?
- *Resilienza.* Come si gestiscono gli errori di breve durata e si mantiene stabile il sistema?
- *Bilanciamento del carico.* In che modo il traffico in ingresso viene distribuito tra più istanze di un servizio?
- *Sicurezza.* In che modo vengono applicati problemi di sicurezza, ad esempio la crittografia a livello di trasporto e la gestione dei certificati?
- *Monitoraggio distribuito.* -In che modo è possibile correlare e acquisire la tracciabilità e il monitoraggio per una singola richiesta tra più servizi consumer?

Sebbene questi problemi possano essere risolti con diverse librerie e Framework, l'implementazione all'interno della codebase può essere costosa, complessa e dispendiosa in termini di tempo. Inoltre, si finisce con una soluzione in cui i problemi di infrastruttura sono associati alla logica di business.

## <a name="service-mesh"></a>Mesh del servizio

Un approccio migliore consiste nel prendere in considerazione una tecnologia nuova e in rapida evoluzione denominata *mesh di servizi*. Una [rete mesh di servizi](https://www.nginx.com/blog/what-is-a-service-mesh/) è un livello di infrastruttura configurabile con funzionalità predefinite per gestire la comunicazione dei servizi e molti dei problemi menzionati in precedenza. Separa questi problemi dal codice aziendale e li sposta in un proxy del servizio, un'istanza di che accompagna ogni servizio. Noto anche come [modello sidecar](https://docs.microsoft.com/azure/architecture/patterns/sidecar), il proxy mesh di servizi viene distribuito in un processo separato per fornire isolamento e incapsulamento dal codice aziendale. Tuttavia, il proxy è strettamente collegato al servizio creato insieme a esso e condividendo il relativo ciclo di vita. Nella figura 6-9 è illustrato questo scenario.

![Rete di servizi con un'auto laterale](./media/service-mesh-with-side-car.png)

**Figura 6-9**. Rete di servizi con un'auto laterale

Nella figura precedente si noti il modo in cui il proxy intercetta e gestisce le comunicazioni tra i microservizi e il cluster.

Una mesh di servizi viene suddivisa logicamente in due componenti diversi: un [piano dati](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc) e un [piano di controllo](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc). La figura 6-10 illustra questi componenti e le relative responsabilità.

![Controllo mesh di servizi e piano dati](./media/istio-control-and-data-plane.png)

**Figura 6-10.** Controllo mesh di servizi e piano dati

Una volta configurata, una mesh del servizio è altamente funzionante. Può recuperare un pool di istanze corrispondente da un endpoint di individuazione del servizio. Può quindi inviare una richiesta a un'istanza specifica, registrando la latenza e il tipo di risposta del risultato. Una mesh può scegliere l'istanza con maggiore probabilità di restituire una risposta rapida in base a molti fattori, inclusa la latenza osservata per le richieste recenti.

Se un'istanza non risponde o non riesce, la mesh può ripetere la richiesta in un'altra istanza. Se un pool restituisce costantemente errori, una mesh può rimuoverla dal pool di bilanciamento del carico per essere ritentata periodicamente successivamente dopo la riparazione. Se una richiesta scade, una mesh può avere esito negativo e quindi ripetere la richiesta. Una mesh acquisisce il comportamento sotto forma di metriche e di traccia distribuita, che possono quindi essere emesse in un sistema di metriche centralizzate.

## <a name="istio-and-envoy"></a>Istio e inviato

Sebbene esistano alcune opzioni di mesh del servizio, [Istio](https://istio.io/docs/concepts/what-is-istio/) è il più popolare al momento della stesura di questo articolo. Una joint venture da IBM, Google e Lyft è un'offerta open source che può essere integrata in un'applicazione distribuita nuova o esistente. Fornisce una soluzione coerente e completa per proteggere, connettere e monitorare i microservizi. Le funzionalità includono:

- Comunicazione da servizio a servizio sicura in un cluster con autenticazione e autorizzazione basate sulle identità complesse.
- Bilanciamento del carico automatico per il traffico HTTP, [gRPC](https://grpc.io/), WEBSOCKET e TCP.
- Controllo con granularità fine del comportamento del traffico con regole di routing avanzate, tentativi, failover e attacchi di errore.
- Un livello di criteri e un'API di configurazione collegabili che supportano i controlli di accesso, i limiti di frequenza e le quote.
- Metriche automatiche, log e tracce per tutto il traffico all'interno di un cluster, tra cui ingresso e uscita del cluster.

Un componente chiave per un'implementazione di Istio è un servizio proxy denominato [proxy di invio](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy). Originato da Lyft e successivamente contribuito al [cloud native Computing Foundation](https://www.cncf.io/) (descritto nel capitolo 1), il proxy inviato viene eseguito insieme a ogni servizio e fornisce una base indipendente dalla piattaforma per le seguenti funzionalità:

- Individuazione dinamica del servizio.
- Bilanciamento del carico.
- Terminazione TLS.
- Proxy HTTP e gRPC.
- Resilienza degli interruttori.
- Controlli di integrità.
- Aggiornamenti in sequenza con distribuzioni [Canarie](https://martinfowler.com/bliki/CanaryRelease.html) .

Come descritto in precedenza, l'inviato viene distribuito come sidecar a ogni microservizio del cluster.

## <a name="integration-with-azure-kubernetes-services"></a>Integrazione con i servizi Kubernetes di Azure

Il cloud di Azure abbraccia Istio e fornisce il supporto diretto per l'it all'interno dei servizi Kubernetes di Azure. I collegamenti seguenti possono essere utili per iniziare:

- [Installazione di Istio in AKS](https://docs.microsoft.com/azure/aks/istio-install)
- [Uso di AKS e Istio](https://docs.microsoft.com/azure/aks/istio-scenario-routing)

>[!div class="step-by-step"]
>[Precedente](infrastructure-resiliency-azure.md)
>[Successivo](monitoring-health.md)
