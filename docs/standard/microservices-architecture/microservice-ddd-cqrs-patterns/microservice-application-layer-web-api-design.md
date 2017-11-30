---
title: Progettare il livello di applicazione microservizio e l'API Web
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Progettare il livello di applicazione microservizio e l'API Web
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 7509b470a30005dd48fa88eefa91f7ed241e4e09
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="designing-the-microservice-application-layer-and-web-api"></a>Progettare il livello di applicazione microservizio e l'API Web

## <a name="using-solid-principles-and-dependency-injection"></a>Utilizzando i principi a tinta unita e inserimento di dipendenze

Tinta unite principi sono critiche tecniche da utilizzare in qualsiasi applicazione moderna e mission-critical, ad esempio lo sviluppo di un microservizio con i modelli di DDD. Tinta unita è l'acronimo di principi fondamentali di cinque gruppi:

-   Principio di responsabilità singolo

-   Principio di apertura/chiusura

-   Principio di sostituzione Liskov

-   Principio di inversione di separazione

-   Principio di inversione di dipendenza

SOLIDO è più su come progettare l'applicazione o microservizio interno livelli e sulle disaccoppiamento dipendenze tra di essi. Non è correlato al dominio, ma per la progettazione tecnica dell'applicazione. Il principio finale, il principio di inversione di dipendenze (DI), consente di separare il livello di infrastruttura dal resto dei livelli, che consente a un'implementazione separata migliore dei livelli DDD.

SEN è un modo per implementare il principio di inversione di dipendenza. È una tecnica per l'implementazione dell'accoppiamento debole tra gli oggetti e le relative dipendenze. Anziché creare direttamente un'istanza di collaboratori o utilizzando i riferimenti statici, gli oggetti che è necessario che una classe per eseguire le azioni sono forniti a (o "inseriti in") della classe. In genere, le classi verranno dichiarare le relative dipendenze attraverso il relativo costruttore, consentendo loro di seguire il principio di dipendenze esplicite. SEN si basa in genere per contenitori specifici che Inversion of Control (IoC). ASP.NET Core fornisce un semplice contenitore IoC incorporato, ma è anche possibile usare il contenitore IoC preferito, ad esempio Autofac o Ninject.

Seguendo i principi a tinta unita, le classi verranno tendenzialmente naturalmente piccole, ben fornita e facilmente testate. Ma come possibile fa a sapere se sono venga introdotto troppe dipendenze in classi? Se si utilizza DI tramite il costruttore, sarà facile rilevare che semplicemente esaminando il numero di parametri per il costruttore. Se sono presenti troppe dipendenze, si tratta in genere un segno (un [codice odore](http://deviq.com/code-smells/)) la classe sta tentando di eccessivo che è probabile che violano il principio di responsabilità singolo.

Occorrere un'altra Guida per coprire CONTINUO in modo dettagliato. Pertanto, questa guida è necessario conoscere solo un minimo di questi argomenti.

#### <a name="additional-resources"></a>Risorse aggiuntive

-   **CONTINUO: Principi fondamentali OOP**
    [*http://deviq.com/solid/*](http://deviq.com/solid/%20)

-   **Inversione di contenitori di controlli e il modello di inserimento di dipendenze**
    [*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)

-   **Steve Smith. Novità è Glue**
    [*http://ardalis.com/new-is-glue*](http://ardalis.com/new-is-glue)


>[!div class="step-by-step"]
[Precedente] (nosql-database-persistenza-infrastructure.md) [Avanti] (microservice-application-layer-implementation-web-api.md)
