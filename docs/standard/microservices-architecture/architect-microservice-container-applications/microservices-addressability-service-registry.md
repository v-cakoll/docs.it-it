---
title: "Microservizi indirizzabilità e Registro di sistema del servizio"
description: "Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Microservizi indirizzabilità e Registro di sistema del servizio"
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 19a0200dadfb90a455de690d880f4eeae4772ed7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="microservices-addressability-and-the-service-registry"></a>Microservizi indirizzabilità e Registro di sistema del servizio

Ogni microservizio ha un nome univoco (URL) che viene utilizzato per risolvere il percorso. Del microservizio deve essere indirizzabili ogni volta che è in esecuzione. Se è necessario che sul computer da cui è in esecuzione un particolare microservizio, operazioni passare errate rapidamente. Nello stesso modo che DNS risolve un URL a un determinato computer, è necessario avere un nome univoco in modo che sia individuabile posizione corrente del microservizio. Microservizi necessario indirizzabili nomi che li rendono indipendente dall'infrastruttura che vengono eseguiti in. Ciò implica che vi sia un'interazione tra la modalità di distribuzione del servizio e come viene individuato, poiché deve essere presente un [registro servizi](http://microservices.io/patterns/service-registry.html). Di conseguenza, quando un computer non riesce, è possibile che il servizio Registro di sistema deve essere in grado di indicare se il servizio è in esecuzione.

Il [modello di servizio Registro di sistema](http://microservices.io/patterns/service-registry.html) è una parte importante dell'individuazione del servizio. Il Registro di sistema è un database contenente i percorsi di rete delle istanze del servizio. Un registro di sistema del servizio deve essere aggiornato e a disponibilità elevata. I client è possibile memorizzare nella cache i percorsi di rete ottenuti dal Registro di sistema del servizio. Tuttavia, tali informazioni alla fine viene aggiornate e i client non è più possono individuare le istanze del servizio. Di conseguenza, un registro di sistema del servizio è costituito da un cluster di server che utilizzano un protocollo di replica per mantenere la coerenza.

In alcuni ambienti di distribuzione microservizio (denominati cluster in modo da rientrare in una sezione successiva), l'individuazione del servizio è incorporato. Ad esempio, all'interno di un ambiente del servizio di contenitore di Azure, Kubernetes e controller di dominio o del sistema operativo con maratona può gestire la registrazione dell'istanza di servizio e annullamento della registrazione. Un proxy vengono anche eseguite in ogni cluster host che svolge il ruolo del router di individuazione sul lato server. Un altro esempio è Azure Service Fabric, che fornisce inoltre un registro del servizio tramite il servizio di denominazione della casella.

Si noti che alcune sovrapposizione tra il Registro di sistema del servizio e il modello di gateway API, che consente di risolvere questo problema anche. Ad esempio, il [Proxy inverso dell'infrastruttura del servizio](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy) è un tipo di implementazione di un Gateway di API che si basa sul servizio Fabrice Naming Service e che consente di risolvere la risoluzione degli indirizzi per i servizi interni.

## <a name="additional-resources"></a>Risorse aggiuntive

-   **Chris Richardson. Modello: Registro del servizio**
    *http://microservices.io/patterns/service-registry.html*

-   **Auth0. Il servizio Registro di sistema**
    [*https://auth0.com/blog/an-introduction-to-microservices-part-3-the-service-registry/*](https://auth0.com/blog/an-introduction-to-microservices-part-3-the-service-registry/)

-   **gabriel Schenker. Individuazione del servizio**
    [*https://lostechies.com/gabrielschenker/2016/01/27/service-discovery/*](https://lostechies.com/gabrielschenker/2016/01/27/service-discovery/)


>[!div class="step-by-step"]
[Precedente] (mantenere-microservizio-apis.md) [Avanti] (microservice-based-composite-ui-shape-layout.md)
