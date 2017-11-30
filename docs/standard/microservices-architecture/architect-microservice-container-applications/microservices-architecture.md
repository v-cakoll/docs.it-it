---
title: Architettura di microservizi
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Architettura di Microservizi
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 5ede1f0ad19270ca6b7556ff1bb7e4cf8ccf7cbe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="microservices-architecture"></a>Architettura di microservizi

Come suggerisce il nome, un'architettura di microservizi è un approccio alla creazione di un'applicazione server come un set di servizi di piccole dimensioni. Ogni servizio viene eseguito in un processo e comunica con altri processi che utilizzano protocolli, ad esempio HTTP/HTTPS, WebSockets, o [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol). Ogni microservizio implementa un dominio end-to-end specifico o una funzionalità di business all'interno di un determinato contesto e ognuna deve essere sviluppata in modo autonomo ed essere distribuita in modo indipendente. Infine, ogni microservizio deve essere proprietario relativo modello di dati correlati di dominio e la logica di dominio (sovranità e gestione dei dati decentralizzata) in base alle tecnologie di archiviazione di dati diversi (SQL, NoSQL) e i diversi linguaggi di programmazione.

Specificare le dimensioni deve essere un microservizio? Quando si sviluppa un microservizio, dimensioni non devono essere l'aspetto importante. Al contrario, il punto importante deve essere creare loosely coupled servizi in modo che sia l'autonomia di sviluppo, distribuzione e scala, per ogni servizio. Naturalmente, se l'identificazione e la progettazione di microservizi, è consigliabile per renderli più piccoli possibile fino a quando non è un numero eccessivo di dipendenze dirette con altri microservizi. Più importanti le dimensioni del microservizio sono di coesione interna che devono essere e sua indipendenza da altri servizi.

Motivo per cui un'architettura di microservizi? In breve, offre flessibilità a lungo termine. Microservizi abilitare maggiore semplicità di gestione nei sistemi altamente scalabile, grandi e complessi in quanto consente di creare applicazioni basate su molti servizi distribuibili in modo indipendente che dispongono di cicli di vita granulare e autonomi.

Un ulteriore vantaggio, microservizi possono scalare orizzontalmente in modo indipendente. Anziché una singola applicazione monolitica che prevedono la scalabilità come un'unità, è invece possibile scalare orizzontalmente microservizi specifico. In questo modo, è possibile ridimensionare solo l'area funzionale che richiede più l'elaborazione dell'alimentazione o rete larghezza di banda per il supporto di richiesta, anziché di scalabilità orizzontale di altre aree dell'applicazione che non richiedono la scalabilità. Ciò significa che risparmi sui costi perché sono necessari meno componenti hardware.

![](./media/image6.png)

**Figura 4-6**. Distribuzione monolitica rispetto all'approccio di microservizi

Come mostrato nella figura 4-6, l'approccio di microservizi consente modifiche agile e iterazioni rapida di ogni microservizio, poiché è possibile modificare le aree specifiche di piccole dimensioni di applicazioni complesse, grandi dimensioni e scalabile.

Architettura di integrazione continua consente di microservizi granulari per le applicazioni e procedure consigliate di recapito continuo. Inoltre accelera la consegna di nuove funzioni nell'applicazione. Composizione accurato delle applicazioni consente inoltre di eseguire e testare microservizi in isolamento ed evolvano in modo autonomo mantenendo deselezionare i contratti tra di essi. Fino a quando non si modifica l'interfacce o contratti, è possibile modificare l'implementazione interna di qualsiasi microservizio o aggiungere nuove funzionalità senza interrompere altre microservizi.

Di seguito sono importanti aspetti per abilitare l'esito positivo entra in produzione con un sistema basato su microservizi:

-   Controlli di monitoraggio e l'integrità dei servizi e dell'infrastruttura.

-   Infrastruttura scalabile per i servizi (vale a dire, cloud e orchestrators).

-   Progettazione di protezione e l'implementazione a più livelli: autenticazione, autorizzazione, la gestione dei segreti, comunicazioni protette e così via.

-   Recapito rapido di applicazioni, in genere con diversi team incentrati sui differenti microservizi.

-   Procedure consigliate di DevOps e CI/CD-ROM e infrastruttura.

Di questi, solo le prime tre sono coperti o introdotte in questa Guida. Ultimi due punti, che sono correlati al ciclo di vita dell'applicazione, sono trattati in altro [contenitore Docker ciclo di vita applicazione con Microsoft Platform e strumenti](https://aka.ms/dockerlifecycleebook) e-book.

## <a name="additional-resources"></a>Risorse aggiuntive

-   **Mark Russinovich. Microservizi: Un revolution applicazione dal cloud**
    [*https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/*](https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/)

-   **Martin Fowler. Microservizi**
    [*http://www.martinfowler.com/articles/microservices.html*](http://www.martinfowler.com/articles/microservices.html)

-   **Martin Fowler. Prerequisiti Microservizio**
    [*http://martinfowler.com/bliki/MicroservicePrerequisites.html*](http://martinfowler.com/bliki/MicroservicePrerequisites.html)

-   **Jimmy Nilsson. Blocco di Cloud Computing**
    [*https://www.infoq.com/articles/CCC-Jimmy-Nilsson*](https://www.infoq.com/articles/CCC-Jimmy-Nilsson)

-   **Cesar de la Torre. Contenitore Docker del ciclo di vita dell'applicazione con Microsoft Platform e strumenti** (scaricabile e-book) [ *https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)




>[!div class="step-by-step"]
[Precedente] (service-oriented-architecture.md) [Avanti] (data-sovranità-per-microservice.md)
