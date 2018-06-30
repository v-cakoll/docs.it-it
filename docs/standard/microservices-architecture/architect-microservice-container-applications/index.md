---
title: Architettura di applicazioni basate su contenitori e microservizi
description: Architettura di microservizi .NET per le applicazioni .NET incluse in contenitori | Architettura di applicazioni .NET basate su contenitori e microservizi
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 185279cb4df70d9896d7e11c995170e7cd214f73
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106814"
---
# <a name="architecting-container--and-microservice-based-applications"></a>Architettura di applicazioni basate su contenitori e microservizi

*I microservizi offrono notevoli vantaggi, ma generano anche nuove problematiche importanti. I modelli di architettura di microservizi sono fondamentali per la creazione di un'applicazione basata su microservizi.*

Negli argomenti precedenti di questa Guida sono stati spiegati i concetti di base sui contenitori e Docker. Le informazioni fornite sono il minimo necessario per iniziare a usare i contenitori. Anche nei casi in cui i contenitori hanno la funzione di abilitatori e sebbene siano adatti per i microservizi, non sono obbligatori per un'architettura di microservizi e molti concetti relativi all'architettura presentati in questa sezione potrebbero essere applicati anche senza i contenitori. Queste istruzioni si concentrano tuttavia sulla combinazione di questi elementi, data l'importanza già descritta dei contenitori.

Le applicazioni aziendali possono essere complesse e spesso sono composte da più servizi anziché da una singola applicazione basata su servizi. In questi casi, è necessario comprendere altri approcci per la creazione dell'architettura, ad esempio i microservizi e alcuni schemi di progettazione basata su domini, oltre ai concetti di orchestrazione dei contenitori. Questo capitolo riguarda non solo i microservizi su contenitori, ma anche qualsiasi applicazione inclusa in un contenitore.

## <a name="container-design-principles"></a>Principi di progettazione dei contenitori

Nel modello di contenitore, un'istanza dell'immagine del contenitore rappresenta un singolo processo. Definendo l'immagine di un contenitore come limite del processo, è possibile creare le primitive che possono essere usate per ridimensionare il processo o suddividerlo in batch.

Quando si progetta un'immagine del contenitore, Dockerfile conterrà una definizione [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/). In questo modo viene definito il processo il cui ciclo di vita controlla il ciclo di vita del contenitore. Al completamento del processo, termina il ciclo di vita del contenitore. I contenitori potrebbero rappresentare processi a esecuzione prolungata come i server Web, ma possono anche rappresentare i processi di breve durata, come i processi batch, che in precedenza potrebbero essere stati implementati come [processi Web](https://docs.microsoft.com/azure/app-service-web/websites-webjobs-resources) di Azure.

Se il processo ha esito negativo, il ciclo di vita del contenitore termina e subentra l'agente di orchestrazione. Se l'agente di orchestrazione è stato configurato per mantenere cinque istanze in esecuzione e una non riesce, crea un'altra istanza del contenitore per sostituire il processo non riuscito. In un processo batch, il processo viene avviato con parametri. Al termine del processo, il lavoro risulta completato. Più avanti in questo materiale sussidiario viene eseguito il drill-down degli agenti di orchestrazione.

In alcune situazioni occorre che più processi vengano eseguiti in un singolo contenitore. In questi casi, poiché può esserci un solo punto di ingresso per ogni contenitore, è possibile eseguire uno script all'interno del contenitore per avviare tutti i programmi necessari. È ad esempio possibile usare [Supervisor](http://supervisord.org/) o uno strumento simile per avviare più processi in un solo contenitore. Anche se è possibile trovare architetture che supportano più processi per ogni contenitore, questo approccio non è tuttavia molto comune.


>[!div class="step-by-step"]
[Precedente](../net-core-net-framework-containers/official-net-docker-images.md)
[Successivo](containerize-monolithic-applications.md)
