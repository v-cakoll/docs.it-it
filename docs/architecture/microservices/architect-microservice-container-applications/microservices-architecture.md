---
title: Architettura di microservizi
description: Architettura di microservizi .NET per applicazioni .NET incluse in contenitori | Il quadro generale dell'architettura di microservizi.
ms.date: 09/20/2018
ms.openlocfilehash: 3cf2a94140042d3cf76b5b63fe4e98638c56dbfe
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68672988"
---
# <a name="microservices-architecture"></a>Architettura di microservizi

Come suggerisce il nome, un'architettura di microservizi è un approccio alla creazione di un'applicazione server come un set di piccoli servizi. Ciò significa che un'architettura di microservizi è principalmente orientata al back-end, anche se l'approccio viene usato anche per il front-end. Ogni servizio viene eseguito nel rispettivo processo e comunica con gli altri processi tramite protocolli quali HTTP/HTTPS, WebSocket o [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol). Ogni microservizio implementa una funzionalità aziendale o un dominio end-to-end specifico all'interno di un determinato limite di contesto. Deve essere inoltre sviluppato in modo autonomo ed essere distribuito in modo indipendente. Ogni microservizio, infine, deve essere proprietario del modello di dati di dominio e della logica di dominio corrispondenti (sovranità e gestione decentralizzata dei dati), che possono essere basati su varie tecnologie di archiviazione dati (SQL, NoSQL) e linguaggi di programmazione diversi.

Quali dimensioni deve avere un microservizio? Quando si sviluppa un microservizio, le dimensioni non hanno molta importanza. È importante invece creare servizi a regime di controllo libero, in modo da avere, per ogni servizio, piena autonomia di sviluppo, distribuzione e scalabilità. Quando si identificano e si progettano microservizi, naturalmente, è consigliabile crearli più piccoli possibile, senza tuttavia avere un numero eccessivo di dipendenze dirette da altri microservizi. Più delle dimensioni, infatti, sono importanti la coesione interna del microservizio e l'indipendenza dagli altri servizi.

Perché un'architettura di microservizi? In breve, offre flessibilità a lungo termine. I microservizi garantiscono una maggiore semplicità di gestione in sistemi grandi, complessi e altamente scalabili, poiché consentono di creare applicazioni basate su molti servizi distribuibili in modo indipendente, ciascuno con cicli di vita autonomi e specifici.

I microservizi, inoltre, possono essere ampliati in modo indipendente. In altre parole, non si ha più un'applicazione monolitica che deve essere ampliata come singola unità, ma è possibile ampliare solo determinati microservizi. È possibile quindi ampliare solo l'area funzionale che richiede più potenza di elaborazione o larghezza di banda di rete per poter supportare la richiesta, senza dover ampliare inutilmente altre aree dell'applicazione. Ne consegue quindi una riduzione dei componenti hardware necessari e, pertanto, un considerevole risparmio economico.

![Nell'approccio monolitico tradizionale l'applicazione ridimensiona clonando l'intera app in più server o macchine virtuali. Nell'approccio con microservizi le funzionalità sono separate in servizi più piccoli, in modo che ognuno di essi si possa ridimensionare in modo indipendente.](./media/image6.png)

**Figura 4-6**. Confronto tra distribuzione monolitica e approccio basato su microservizi

Come illustrato nella figura 4-6, l'approccio basato su microservizi consente modifiche flessibili e una rapida iterazione di ogni microservizio, offrendo la possibilità di modificare piccole aree specifiche di applicazioni complesse, scalabili e di grandi dimensioni.

La progettazione di applicazioni basate su microservizi con granularità fine consente processi di integrazione continua e recapito continuo. Accelera inoltre la distribuzione di nuove funzioni nell'applicazione. La composizione di applicazioni con granularità fine consente inoltre di eseguire e testare microservizi in isolamento ed evolverli in modo autonomo, pur mantenendo contratti precisi tra di essi. A condizione che non vengano apportate modifiche alle interfacce o ai contratti, è possibile modificare l'implementazione interna di qualsiasi microservizio o aggiungere nuove funzionalità senza interrompere gli altri microservizi.

Di seguito sono elencati alcuni aspetti importanti per portare a termine correttamente la produzione di un sistema basato su microservizi:

- Monitoraggio e controlli di integrità dei servizi e dell'infrastruttura.

- Infrastruttura scalabile per i servizi (ovvero, cloud e agenti di orchestrazione).

- Progettazione e implementazione della sicurezza a più livelli: autenticazione, autorizzazione, gestione dei segreti, comunicazioni protette e così via.

- Distribuzione rapida delle applicazioni, in genere con più team di lavoro incentrati su diversi microservizi.

- Infrastruttura e processi DevOps e di integrazione continua/recapito continuo.

Solo i prime tre aspetti sono descritti o introdotti nella presente guida. Gli ultimi due punti, correlati al ciclo di vita delle applicazioni, sono trattati nell'e-book [Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft](https://aka.ms/dockerlifecycleebook).

## <a name="additional-resources"></a>Risorse aggiuntive

- **Mark Russinovich. Microservices: An application revolution powered by the cloud** \ (Microservizi: una rivoluzione delle applicazioni consentita dal cloud)
  <https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/>

- **Martin Fowler. Microservizi** \
  <https://www.martinfowler.com/articles/microservices.html>

- **Martin Fowler. Microservice Prerequisites** \ (Prerequisiti dei microservizi)
  <https://martinfowler.com/bliki/MicroservicePrerequisites.html>

- **Jimmy Nilsson. Chunk Cloud Computing** \ (Cloud computing in blocchi)
  <https://www.infoq.com/articles/CCC-Jimmy-Nilsson>

- **Cesar de la Torre. Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft** (e-book scaricabile) \
  <https://aka.ms/dockerlifecycleebook>

>[!div class="step-by-step"]
>[Precedente](service-oriented-architecture.md)
>[Successivo](data-sovereignty-per-microservice.md)
