---
title: Modelli di comunicazione cloud nativi
description: Informazioni sui principali problemi di comunicazione del servizio nelle applicazioni native del cloud
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: 3d678df44b5fef68427846e59f446b7408795625
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614214"
---
# <a name="cloud-native-communication-patterns"></a>Modelli di comunicazione cloud nativi

Quando si costruisce un sistema nativo del cloud, la comunicazione diventa una decisione di progettazione significativa. In che modo un'applicazione client front-end comunica con un microservizio back-end? In che modo i microservizi back-end comunicano tra loro? Quali sono i principi, i modelli e le procedure consigliate da considerare quando si implementa la comunicazione nelle applicazioni native del cloud?

## <a name="communication-considerations"></a>Considerazioni sulla comunicazione

In un'applicazione monolitica, la comunicazione è semplice. I moduli di codice vengono eseguiti insieme nello stesso spazio eseguibile (processo) in un server. Questo approccio può avere vantaggi a livello di prestazioni, in quanto tutto viene eseguito insieme nella memoria condivisa, ma comporta un codice strettamente collegato che diventa difficile da gestire, evolvere e ridimensionare.

I sistemi nativi del cloud implementano un'architettura basata su microservizi con molti microservizi indipendenti e piccoli. Ogni microservizio viene eseguito in un processo separato ed è in genere eseguito all'interno di un contenitore distribuito in un *cluster*.

Un cluster raggruppa un pool di macchine virtuali insieme per formare un ambiente a disponibilità elevata. Sono gestite con uno strumento di orchestrazione, responsabile della distribuzione e della gestione dei microservizi in contenitori. La figura 4-1 Mostra un cluster [Kubernetes](https://kubernetes.io) distribuito nel cloud di Azure con i [servizi di Azure Kubernetes](https://docs.microsoft.com/azure/aks/intro-kubernetes)completamente gestiti.

![Un cluster Kubernetes in Azure](./media/kubernetes-cluster-in-azure.png)

**Figura 4-1**. Un cluster Kubernetes in Azure

Attraverso il cluster, i microservizi comunicano tra loro tramite API e tecnologie di messaggistica.

Sebbene forniscano molti vantaggi, i microservizi non sono disponibili in un pranzo gratuito. Le chiamate al metodo locale in-process tra i componenti vengono ora sostituite con chiamate di rete. Ogni microservizio deve comunicare tramite un protocollo di rete, che aggiunge complessità al sistema:

- La congestione della rete, la latenza e gli errori temporanei rappresentano un problema costante.

- La resilienza, ovvero il nuovo tentativo di richieste non riuscite, è essenziale.

- Alcune chiamate devono essere [idempotente](https://www.restapitutorial.com/lessons/idempotency.html) come per tenere lo stato coerente.

- Ogni microservizio deve autenticare e autorizzare le chiamate.

- Ogni messaggio deve essere serializzato e quindi deserializzato, che può essere costoso.

- La crittografia o la decrittografia del messaggio diventa importante.

Il libro [microservizi .NET: l'architettura per le applicazioni .NET in contenitori](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook), disponibile gratuitamente da Microsoft, fornisce una copertura dettagliata dei modelli di comunicazione per le applicazioni di microservizi. In questo capitolo viene fornita una panoramica di alto livello di questi modelli insieme alle opzioni di implementazione disponibili nel cloud di Azure.

In questo capitolo verranno innanzitutto indirizzate le comunicazioni tra le applicazioni front-end e i microservizi back-end. Verranno quindi esaminati i microservizi back-end che comunicano tra loro. Esamineremo la tecnologia di comunicazione up and gRPC. Infine, verranno esaminati nuovi modelli di comunicazione innovativi con la tecnologia mesh di servizi. Si vedrà anche come il cloud di Azure fornisca diversi tipi di *Servizi* di supporto per supportare la comunicazione nativa del cloud.

>[!div class="step-by-step"]
>[Precedente](other-deployment-options.md) 
> [Avanti](front-end-communication.md)
