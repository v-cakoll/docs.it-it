---
title: Architettura di microservizi
description: Architettura dei microservizi .NET per le applicazioni .NET in contenitori | Architettura di microservizi
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 9bcaacce323ed9afa482660f409312f9a1b82cfa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="microservices-architecture"></a>Architettura di microservizi

Come suggerisce il nome, un'architettura di microservizi è un approccio alla creazione di un'applicazione server come un set di piccoli servizi. Ogni servizio viene eseguito nel rispettivo processo e comunica con gli altri processi tramite protocolli quali HTTP/HTTPS, WebSocket o [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol). Ogni microservizio implementa una funzionalità aziendale o un dominio end-to-end specifico all'interno di un determinato limite di contesto. Deve essere inoltre sviluppato in modo autonomo ed essere distribuito in modo indipendente. Ogni microservizio, infine, deve essere proprietario del modello di dati di dominio e della logica di dominio corrispondenti (sovranità e gestione decentralizzata dei dati), che possono essere basati su varie tecnologie di archiviazione dati (SQL, NoSQL) e vari linguaggi di programmazione.

Quali dimensioni deve avere un microservizio? Quando si sviluppa un microservizio, le dimensioni non hanno molta importanza. È importante invece creare servizi a regime di controllo libero, in modo da avere, per ogni servizio, piena autonomia di sviluppo, distribuzione e scalabilità. Quando si identificano e si progettano microservizi, naturalmente, è consigliabile crearli più piccoli possibile, senza tuttavia avere un numero eccessivo di dipendenze dirette da altri microservizi. Più delle dimensioni, infatti, sono importanti la coesione interna del microservizio e l'indipendenza dagli altri servizi.

Perché un'architettura di microservizi? In breve, offre flessibilità a lungo termine. I microservizi garantiscono una maggiore semplicità di gestione in sistemi grandi, complessi e altamente scalabili, poiché consentono di creare applicazioni basate su molti servizi distribuibili in modo indipendente, ciascuno con cicli di vita autonomi e specifici.

I microservizi, inoltre, possono essere ampliati in modo indipendente. In altre parole, non si ha più un'applicazione monolitica che deve essere ampliata come singola unità, ma è possibile ampliare solo determinati microservizi. È possibile quindi ampliare solo l'area funzionale che richiede più potenza di elaborazione o larghezza di banda di rete per poter supportare la richiesta, senza dover ampliare inutilmente altre aree dell'applicazione. Ne consegue quindi una riduzione dei componenti hardware necessari e, pertanto, un considerevole risparmio economico.

![](./media/image6.png)

**Figura 4-6**. Confronto tra distribuzione monolitica e approccio basato su microservizi

Come illustrato nella figura 4-6, l'approccio basato su microservizi consente modifiche flessibili e una rapida iterazione di ogni microservizio, offrendo la possibilità di modificare piccole aree specifiche di applicazioni complesse, scalabili e di grandi dimensioni.

La progettazione di applicazioni basate su microservizi con granularità fine consente processi di integrazione continua e recapito continuo. Accelera inoltre la distribuzione di nuove funzioni nell'applicazione. La composizione di applicazioni con granularità fine consente inoltre di eseguire e testare microservizi in isolamento ed evolverli in modo autonomo, pur mantenendo contratti precisi tra di essi. A condizione che non vengono apportate modifiche alle interfacce o ai contratti, infatti, è possibile modificare l'implementazione interna di qualsiasi microservizio o aggiungere nuove funzionalità senza interrompere l'esecuzione di altri microservizi.

Di seguito sono elencati alcuni aspetti importanti per portare a termine correttamente la produzione di un sistema basato su microservizi:

-   Monitoraggio e controlli di integrità dei servizi e dell'infrastruttura.

-   Infrastruttura scalabile per i servizi (ovvero, cloud e agenti di orchestrazione).

-   Progettazione e implementazione della sicurezza a più livelli: autenticazione, autorizzazione, gestione dei segreti, comunicazioni protette e così via.

-   Distribuzione rapida delle applicazioni, in genere con più team di lavoro incentrati su diversi microservizi.

-   Infrastruttura e processi DevOps e di integrazione continua/recapito continuo.

Solo i prime tre aspetti sono descritti o introdotti nella presente guida. Gli ultimi due punti, correlati al ciclo di vita delle applicazioni, sono trattati nell'e-book [Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft](https://aka.ms/dockerlifecycleebook).

## <a name="additional-resources"></a>Risorse aggiuntive

-   **Mark Russinovich. Microservices: An application revolution powered by the cloud**
    [*https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/*](https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/) (Microservizi: una rivoluzione delle applicazioni consentita dal cloud)

-   **Martin Fowler. Microservices**
    [*https://www.martinfowler.com/articles/microservices.html*](https://www.martinfowler.com/articles/microservices.html) (Microservizi)

-   **Martin Fowler. Microservice Prerequisites**
    [*https://martinfowler.com/bliki/MicroservicePrerequisites.html*](https://martinfowler.com/bliki/MicroservicePrerequisites.html) (Prerequisiti dei microservizi)

-   **Jimmy Nilsson. Chunk Cloud Computing**
    [*https://www.infoq.com/articles/CCC-Jimmy-Nilsson*](https://www.infoq.com/articles/CCC-Jimmy-Nilsson) (Cloud computing in blocchi)

-   **Cesar de la Torre. Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft**  (e-book scaricabile) [*https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)




>[!div class="step-by-step"]
[Precedente] (service-oriented-architecture.md) [Successivo] (data-sovereignty-per-microservice.md)
