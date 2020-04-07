---
title: App candidate per il cloud nativo
description: Informazioni sui tipi di applicazioni che traggono vantaggio da un approccio basato sul cloud
author: robvet
ms.date: 03/31/2020
ms.openlocfilehash: 8e58f5bd3aa0a4503ea73ab454e42e863eb0bb5d
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805620"
---
# <a name="candidate-apps-for-cloud-native"></a>App candidate per il cloud nativo

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Guarda le app nel tuo portfolio. Quanti di loro si qualificano per un'architettura cloud-native? Tutti? Forse un po'?

Applicando un'analisi costi/benefici, c'è una buona probabilità che la maggior parte non supporti il prezzo pesante richiesto per essere cloud nativo. Il costo di essere cloud nativo supererebbe di gran lunga il valore aziendale dell'applicazione.

Che tipo di applicazione potrebbe essere un candidato per cloud native?

- Un sistema aziendale di grandi dimensioni e strategico che deve evolvere costantemente le capacità/caratteristiche aziendali

- Un'applicazione che richiede un'alta velocità di rilascio - con alta sicurezza

- Un sistema con il quale le singole funzionalità devono essere rilasciate *senza* una ridistribuzione completa dell'intero sistema

- Un'applicazione sviluppata da team con esperienza in diversi stack tecnologici

- Un'applicazione con componenti che devono essere scalati in modo indipendente

Poi ci sono i sistemi legacy. Anche se tutti vorremmo creare nuove applicazioni, siamo spesso responsabili della modernizzazione dei carichi di lavoro legacy che sono fondamentali per l'azienda. Nel corso del tempo, un'applicazione legacy potrebbe essere scomposta in microservizi, in contenitoratizzata e, infine, "ripiattaforma" in un'architettura cloud-native.

### <a name="modernizing-legacy-apps"></a>Modernizzazione delle app legacy

L'e-book gratuito Microsoft [Modernize existing .NET applications with Azure cloud and Windows Containers](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook) fornisce indicazioni per la migrazione dei carichi di lavoro locali nel cloud. Figura 1-10 mostra che non esiste una singola strategia one-size-fits-all per la modernizzazione delle applicazioni legacy.

![Strategie per la migrazione dei carichi di lavoro legacy](./media/strategies-for-migrating-legacy-workloads.png)

**Figura 1-10**. Strategie per la migrazione dei carichi di lavoro legacy

Le app monolitiche non critiche traggono in gran parte vantaggio da una rapida migrazione lift-and-shift ([Cloud Infrastructure-Ready).](../modernize-with-azure-containers/lift-and-shift-existing-apps-azure-iaas.md) In questo caso, il carico di lavoro locale viene ospitato nuovamente in una macchina virtuale basata su cloud, senza modifiche. Questo approccio usa il [modello IaaS (Infrastructure as a Service).](https://azure.microsoft.com/overview/what-is-iaas/) Azure include diversi strumenti, ad esempio [Azure Migrate](https://azure.microsoft.com/services/azure-migrate/), Azure [Site Recovery](https://azure.microsoft.com/services/site-recovery/)e Azure Database [Migration Service](https://azure.microsoft.com/campaigns/database-migration/) per semplificare lo spostamento di questo tipo. Sebbene questa strategia possa produrre alcuni risparmi sui costi, tali applicazioni in genere non erano progettate per sbloccare e sfruttare i vantaggi del cloud computing.

Le app monolitiche che sono fondamentali per l'azienda spesso traggono vantaggio da una migrazione lift-and-shift migliorata (*Cloud Optimized).* Questo approccio include ottimizzazioni di distribuzione che abilitano i servizi cloud chiave, senza modificare l'architettura di base dell'applicazione. Ad esempio, è possibile [contenitoriare](https://docs.microsoft.com/virtualization/windowscontainers/about/) l'applicazione e distribuirla in un agente di orchestrazione contenitore, ad esempio [Servizi di Azure Kubernetes](https://azure.microsoft.com/services/kubernetes-service/), descritti più avanti in questo libro. Una volta nel cloud, l'applicazione potrebbe utilizzare altri servizi cloud, ad esempio database, code di messaggi, monitoraggio e memorizzazione nella cache distribuita.

Infine, le app monolitiche che eseguono funzioni aziendali strategiche potrebbero trarre il massimo vantaggio da un approccio *Cloud-Native,* l'oggetto di questo libro. Questo approccio fornisce agilità e velocità. Ma, si tratta di un costo di ripiattaforma, riprogettazione e riscrittura del codice.

Se tu e il tuo team riteniamo che un approccio nativo cloud sia appropriato, è opportuno razionalizzare la decisione con l'organizzazione. Qual è esattamente il problema aziendale che verrà risolto da un approccio nativo cloud? Come si allineerebbe alle esigenze aziendali?

- Rilasci rapidi di funzionalità con maggiore sicurezza?

- Scalabilità dettagliata: utilizzo delle risorse più efficiente?

- Migliorata la resilienza del sistema?

- Miglioramento delle prestazioni del sistema?

- Più visibilità sulle operazioni?

- Fondiare piattaforme di sviluppo e archivi dati per arrivare allo strumento migliore per il lavoro?

- Investimenti applicativi a prova di futuro?

La giusta strategia di migrazione dipende dalle priorità organizzative e dai sistemi di destinazione. Per molti, può essere più conveniente ottimizzare il cloud di un'applicazione monolitica o aggiungere servizi con granularità grossolana a un'app a più livelli. In questi casi, è comunque possibile usare completamente le funzionalità PaaS cloud, come quelle offerte dal servizio app di Azure.In these cases, you can still make full use of cloud PaaS capabilities like the offered by Azure App Service.

## <a name="summary"></a>Summary

In questo capitolo è stato introdotto l'elaborazione nativa del cloud. È stata fornita una definizione insieme alle funzionalità chiave che guidano un'applicazione cloud-native. Abbiamo esaminato i tipi di applicazioni che potrebbero giustificare questo investimento e questo sforzo.

Con l'introduzione dietro, ora ci immerviamo a uno sguardo molto più dettagliato al cloud native.

### <a name="references"></a>Riferimenti

- [Cloud Native Computing Foundation](https://www.cncf.io/)

- [Microservizi .NET: architettura per le applicazioni .NET containerizzate](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)

- [Modernizza le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook)

- [Cloud Native Patterns di Cornelia Davis](https://www.manning.com/books/cloud-native-patterns)

- [Oltre l'applicazione a dodici fattori](https://content.pivotal.io/blog/beyond-the-twelve-factor-app)

- [Che cos'è l'infrastruttura come codiceWhat is Infrastructure as Code](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code)

- [Micro Deploy di Uber Engineering: Distribuzione quotidiana con fiducia](https://eng.uber.com/micro-deploy/)

- [Come Netflix distribuisce il codice](https://www.infoq.com/news/2013/06/netflix/)

- [Controllo dell'overload per la scalabilità dei microservizi di WeChat](https://www.cs.columbia.edu/~ruigu/papers/socc18-final100.pdf)

>[!div class="step-by-step"]
>[Successivo](definition.md)
>[precedente](introduce-eshoponcontainers-reference-app.md)
