---
title: App candidate per cloud native
description: Informazioni sui tipi di applicazioni che traggono vantaggio da un approccio nativo per il cloud
author: robvet
ms.date: 05/14/2020
ms.openlocfilehash: b907a17b2351bc4ffe49fd6eb6f5963b209d00db
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614240"
---
# <a name="candidate-apps-for-cloud-native"></a>App candidate per cloud native

Esaminare le app nel portfolio. Quanti di essi sono idonei per un'architettura nativa del cloud? Tutti? Forse?

Applicando un'analisi costi/vantaggi, è possibile che la maggior parte dei prezzi non supporti il pesante tag di prezzo necessario per il cloud nativo. Il costo di un cloud nativo è di gran lunga superiore al valore aziendale dell'applicazione.

Quale tipo di applicazione può essere un candidato per il cloud nativo?

- Sistema aziendale strategico che deve sviluppare costantemente funzionalità/funzionalità aziendali

- Un'applicazione che richiede una velocità di rilascio elevata, con attendibilità elevata

- Sistema con cui è necessario rilasciare le singole funzionalità *senza* una ridistribuzione completa dell'intero sistema

- Un'applicazione sviluppata da team con competenze in diversi stack di tecnologie

- Applicazione con componenti che devono essere ridimensionati in modo indipendente

Sono quindi presenti sistemi legacy. Per quanto riguarda la creazione di nuove applicazioni, è spesso responsabile della modernizzazione dei carichi di lavoro legacy cruciali per l'azienda. Nel corso del tempo, un'applicazione legacy potrebbe essere scomposta in microservizi, in contenitori e infine "ripiattaforma" in un'architettura nativa del cloud.

### <a name="modernizing-legacy-apps"></a>Modernizzazione di app legacy

L'e-book gratuito Microsoft [modernizza le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook) fornisce indicazioni per la migrazione dei carichi di lavoro locali nel cloud. La figura 1-10 Mostra che non è disponibile una singola strategia unica, unica per la modernizzazione delle applicazioni legacy.

![Strategie per la migrazione di carichi di lavoro legacy](./media/strategies-for-migrating-legacy-workloads.png)

**Figura 1-10**. Strategie per la migrazione di carichi di lavoro legacy

Le app monolitiche che non sono in gran parte critiche traggono vantaggio da una rapida migrazione (pronta per l'[infrastruttura cloud](../modernize-with-azure-containers/lift-and-shift-existing-apps-azure-iaas.md)). In questo caso, il carico di lavoro locale viene riallocato a una macchina virtuale basata sul cloud, senza modifiche. Questo approccio usa il [modello IaaS (infrastruttura distribuita come servizio)](https://azure.microsoft.com/overview/what-is-iaas/). Azure include diversi strumenti, ad esempio [Azure migrate](https://azure.microsoft.com/services/azure-migrate/), [Azure Site Recovery](https://azure.microsoft.com/services/site-recovery/)e il [servizio migrazione del database di Azure](https://azure.microsoft.com/campaigns/database-migration/) per semplificare il passaggio. Sebbene questa strategia possa produrre risparmi in termini di costi, tali applicazioni in genere non sono state progettate per sbloccare e sfruttare i vantaggi di cloud computing.

Le app monolitiche cruciali per l'azienda traggono spesso vantaggio da una migrazione migliorata (*ottimizzata*per il cloud). Questo approccio include le ottimizzazioni di distribuzione che abilitano i servizi cloud principali, senza modificare l'architettura di base dell'applicazione. Ad esempio, è possibile [distribuire](https://docs.microsoft.com/virtualization/windowscontainers/about/) l'applicazione e distribuirla in un agente di orchestrazione del contenitore, come i [Servizi Kubernetes di Azure](https://azure.microsoft.com/services/kubernetes-service/), illustrati più avanti in questo libro. Una volta nel cloud, l'applicazione può utilizzare altri servizi cloud, ad esempio database, code di messaggi, monitoraggio e Caching distribuito.

Infine, le app monolitiche che eseguono funzioni aziendali strategiche possono trarre il massimo vantaggio da un approccio *nativo del cloud* , l'oggetto di questo libro. Questo approccio offre agilità e velocità. Ma comporta un costo per la ricreazione, la riprogettazione e la riscrittura del codice.

Se l'utente e il team ritengono che un approccio nativo per il cloud sia appropriato, è necessario razionalizzare la decisione con l'organizzazione. Qual è esattamente il problema aziendale che verrà risolto da un approccio nativo per il cloud? In che modo si allineano alle esigenze aziendali?

- Versioni rapide delle funzionalità con maggiore fiducia?

- Scalabilità con granularità fine: uso più efficiente delle risorse?

- Maggiore resilienza del sistema?

- Miglioramento delle prestazioni del sistema

- Maggiore visibilità sulle operazioni?

- Piattaforme di sviluppo e archivi dati di Blend per arrivare allo strumento migliore per il processo?

- Investimento per applicazioni future?

La strategia di migrazione corretta dipende dalle priorità dell'organizzazione e dai sistemi di destinazione. Per molti, può essere più conveniente ottimizzare il cloud di un'applicazione monolitica o aggiungere servizi con granularità grossolana a un'app a più livelli. In questi casi, è comunque possibile sfruttare appieno le funzionalità di PaaS cloud come quelle offerte dal servizio app Azure.

## <a name="summary"></a>Summary

In questo capitolo è stato introdotto il cloud native computing. È stata fornita una definizione insieme alle funzionalità principali che guidano un'applicazione nativa del cloud. Sono stati esaminati i tipi di applicazioni che potrebbero giustificare questo investimento e impegno.

Con l'introduzione, viene ora analizzato in modo molto più dettagliato il cloud nativo.

### <a name="references"></a>Riferimenti

- [Cloud native Computing Foundation](https://www.cncf.io/)

- [Microservizi .NET: architettura per le applicazioni .NET in contenitori](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)

- [Modernizzare le applicazioni .NET esistenti con cloud di Azure e i contenitori di Windows](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook)

- [Modelli nativi del cloud di Cornelia Davis](https://www.manning.com/books/cloud-native-patterns)

- [Oltre l'applicazione a dodici fattori](https://content.pivotal.io/blog/beyond-the-twelve-factor-app)

- [Che cos'è l'infrastruttura come codice](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code)

- [Micro deploy di uber Engineering: distribuzione giornaliera con sicurezza](https://eng.uber.com/micro-deploy/)

- [Come Netflix distribuisce il codice](https://www.infoq.com/news/2013/06/netflix/)

- [Controllo dell'overload per la scalabilità di microservizi WeChat](https://www.cs.columbia.edu/~ruigu/papers/socc18-final100.pdf)

>[!div class="step-by-step"]
>[Precedente](definition.md) 
> [Avanti](introduce-eshoponcontainers-reference-app.md)
