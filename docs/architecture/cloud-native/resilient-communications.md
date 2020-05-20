---
title: Comunicazione resiliente
description: Architettura di app .NET cloud native per Azure | Comunicazione resiliente
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: 33e4c03c1f3d8c01f72c588326fbb0bdfa512cdd
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613746"
---
# <a name="resilient-communications"></a>Comunicazioni resilienti

In questo libro abbiamo adottato un approccio architetturale basato su microservizi. Sebbene tale architettura offra vantaggi importanti, presenta diverse problemi:

- *Comunicazione di rete out-of-process.* Ogni microservizio comunica tramite un protocollo di rete che introduce congestioni di rete, latenza ed errori temporanei.

- *Individuazione del servizio.* In che modo i microservizi scoprono e comunicano tra loro durante l'esecuzione in un cluster di computer con indirizzi IP e porte personali?

- *Resilienza.* Come si gestiscono gli errori di breve durata e si mantiene stabile il sistema?

- *Bilanciamento del carico.* In che modo il traffico in ingresso viene distribuito tra più istanze di un microservizio?

- *Sicurezza.* In che modo vengono applicati problemi di sicurezza, ad esempio la crittografia a livello di trasporto e la gestione dei certificati?

- *Monitoraggio distribuito.* -In che modo è possibile correlare e acquisire la tracciabilità e il monitoraggio per una singola richiesta tra più microservizi?

È possibile risolvere questi problemi con librerie e Framework diversi, ma l'implementazione può essere costosa, complessa e dispendiosa in termini di tempo. Si finiranno anche i problemi di infrastruttura associati alla logica di business.

## <a name="service-mesh"></a>Mesh del servizio

Un approccio migliore è una tecnologia in evoluzione denominata *mesh di servizi*. Una [rete mesh di servizi](https://www.nginx.com/blog/what-is-a-service-mesh/) è un livello di infrastruttura configurabile con funzionalità predefinite per gestire la comunicazione dei servizi e gli altri problemi menzionati in precedenza. Per separare questi problemi, spostarli in un proxy del servizio. Il proxy viene distribuito in un processo separato (denominato [sidecar](https://docs.microsoft.com/azure/architecture/patterns/sidecar)) per fornire isolamento dal codice business. Tuttavia, il sidecar è collegato al servizio, che viene creato con esso e ne condivide il ciclo di vita. Nella figura 6-7 è illustrato questo scenario.

![Rete di servizi con un'auto laterale](./media/service-mesh-with-side-car.png)

**Figura 6-7**. Rete di servizi con un'auto laterale

Nella figura precedente si noti il modo in cui il proxy intercetta e gestisce le comunicazioni tra i microservizi e il cluster.

Una mesh di servizi viene suddivisa logicamente in due componenti diversi: un [piano dati](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc) e un [piano di controllo](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc). La figura 6-8 illustra questi componenti e le relative responsabilità.

![Controllo mesh di servizi e piano dati](./media/istio-control-and-data-plane.png)

**Figura 6-8.** Controllo mesh di servizi e piano dati

Una volta configurata, una mesh del servizio è altamente funzionante. Può recuperare un pool di istanze corrispondente da un endpoint di individuazione del servizio. La mesh può quindi inviare una richiesta a un'istanza specifica, registrando la latenza e il tipo di risposta del risultato. Una mesh può scegliere l'istanza con maggiore probabilità di restituire una risposta rapida in base a molti fattori, inclusa la latenza osservata per le richieste recenti.

Se un'istanza non risponde o non riesce, la mesh tenterà di ripetere la richiesta in un'altra istanza. Se vengono restituiti errori, una mesh eliminerà l'istanza dal pool di bilanciamento del carico e lo ricaricherà dopo la correzione. Se una richiesta scade, una mesh può avere esito negativo e quindi ripetere la richiesta. Una mesh acquisisce ed emette metriche e analisi distribuite in un sistema di metriche centralizzate.

## <a name="istio-and-envoy"></a>Istio e inviato

Sebbene esistano alcune opzioni di mesh del servizio, [Istio](https://istio.io/docs/concepts/what-is-istio/) è il più diffuso al momento della stesura di questo articolo. Istio è una joint venture tra IBM, Google e Lyft. Si tratta di un'offerta open source che può essere integrata in un'applicazione distribuita nuova o esistente. La tecnologia fornisce una soluzione coerente e completa per proteggere, connettere e monitorare i microservizi. Le funzionalità includono:

- Comunicazione da servizio a servizio sicura in un cluster con autenticazione e autorizzazione basate sulle identità complesse.
- Bilanciamento del carico automatico per il traffico HTTP, [gRPC](https://grpc.io/), WEBSOCKET e TCP.
- Controllo con granularità fine del comportamento del traffico con regole di routing avanzate, tentativi, failover e attacchi di errore.
- Un livello di criteri e un'API di configurazione collegabili che supportano i controlli di accesso, i limiti di frequenza e le quote.
- Metriche automatiche, log e tracce per tutto il traffico all'interno di un cluster, tra cui ingresso e uscita del cluster.

Un componente chiave per un'implementazione di Istio è un servizio proxy denominato [proxy di invio](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy). Viene eseguito insieme a ogni servizio e fornisce una base indipendente dalla piattaforma per le seguenti funzionalità:

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

### <a name="references"></a>Riferimenti

- [Polly](http://www.thepollyproject.org/)

- [Modello di ripetizione dei tentativi](https://docs.microsoft.com/azure/architecture/patterns/retry)

- [Modello di interruttore](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)

- [White paper sulla resilienza in Azure](https://azure.microsoft.com/mediahandler/files/resourcefiles/resilience-in-azure-whitepaper/Resilience%20in%20Azure.pdf)

- [latenza di rete](https://www.techopedia.com/definition/8553/network-latency)

- [Ridondanza](https://docs.microsoft.com/azure/architecture/guide/design-principles/redundancy)

- [replica geografica](https://docs.microsoft.com/azure/sql-database/sql-database-active-geo-replication)

- [Gestione traffico di Azure](https://docs.microsoft.com/azure/traffic-manager/traffic-manager-overview)

- [Indicazioni sulla scalabilità automatica](https://docs.microsoft.com/azure/architecture/best-practices/auto-scaling)

- [Istio](https://istio.io/docs/concepts/what-is-istio/)

- [Proxy inviato](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy)

>[!div class="step-by-step"]
>[Precedente](infrastructure-resiliency-azure.md) 
> [Avanti](monitoring-health.md)
