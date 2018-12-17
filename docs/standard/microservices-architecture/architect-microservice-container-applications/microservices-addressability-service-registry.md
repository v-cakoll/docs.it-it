---
title: Indirizzabilità dei microservizi e registro del servizio
description: Informazioni sul ruolo dei registri di immagini del contenitore nell'architettura di microservizi.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/20/2018
ms.openlocfilehash: 60afb2e06c0c9a37104a82a74de016da5c134a61
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53145845"
---
# <a name="microservices-addressability-and-the-service-registry"></a>Indirizzabilità dei microservizi e registro del servizio

Ogni microservizio ha un nome univoco (URL) che viene usato per risolverne il percorso. Il microservizio deve essere indirizzabile ovunque venga eseguito. Se è necessario pensare su quale computer è in esecuzione un determinato microservizio, qualcosa non va. Analogamente al processo con cui il DNS risolve un URL in un determinato computer, il microservizio deve avere un nome univoco in modo che la sua posizione corrente sia facilmente individuabile. I microservizi devono avere nomi indirizzabili che li rendono indipendenti dall'infrastruttura su cui sono in esecuzione. Ciò implica che vi sia un'interazione tra il modo in cui il servizio viene distribuito e il modo in cui viene individuato perché è necessario un [registro del servizio](https://microservices.io/patterns/service-registry.html). In caso di errore in un computer, il servizio registro deve essere in grado di indicare dove è in esecuzione il servizio.

Lo [schema del registro del servizio](https://microservices.io/patterns/service-registry.html) è un componente essenziale per l'individuazione del servizio. Il registro è costituito invece da un database contenente i percorsi di rete delle istanze del servizio. Un registro del servizio deve essere sempre aggiornato e ad alta disponibilità. I client possono memorizzare nella cache i percorsi di rete ottenuti dal registro del servizio. Queste informazioni, tuttavia, diventano presto obsolete e i client non riescono più a individuare le istanze del servizio. È per questo motivo che il registro del servizio è costituito da un cluster di server che usano un protocollo di replica per mantenere la coerenza.

In alcuni ambienti di distribuzione dei microservizi (denominati cluster e illustrati in una sezione successiva), l'individuazione del servizio è una procedura predefinita. Ad esempio, nell'ambiente di un servizio contenitore di Azure con Kubernetes (AKS) è possibile gestire le procedure di registrazione e annullamento della registrazione delle istanze del servizio. Viene inoltre eseguito un proxy su ogni cluster host che svolge il ruolo di router di individuazione sul lato server. Un altro esempio è Azure Service Fabric, che offre un registro del servizio tramite il servizio di denominazione predefinito.

Si noti che esiste una certa sovrapposizione tra il registro del servizio e lo schema del gateway API, altro aspetto che contribuisce a risolvere il problema. Il [proxy inverso di Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy), ad esempio, è un tipo di implementazione di un gateway API basato su Service Fabric Naming Service, che semplifica la risoluzione degli indirizzi dei servizi interni.

## <a name="additional-resources"></a>Risorse aggiuntive

- **Chris Richardson. Modello: Registro del servizio** \
  [*https://microservices.io/patterns/service-registry.html*](https://microservices.io/patterns/service-registry.html)

- **Auth0. Il registro del servizio** \
  [*https://auth0.com/blog/an-introduction-to-microservices-part-3-the-service-registry/*](https://auth0.com/blog/an-introduction-to-microservices-part-3-the-service-registry/)

- **Gabriel Schenker. Individuazione del servizio** \
  [*https://lostechies.com/gabrielschenker/2016/01/27/service-discovery/*](https://lostechies.com/gabrielschenker/2016/01/27/service-discovery/)

>[!div class="step-by-step"]
>[Precedente](maintain-microservice-apis.md)
>[Successivo](microservice-based-composite-ui-shape-layout.md)