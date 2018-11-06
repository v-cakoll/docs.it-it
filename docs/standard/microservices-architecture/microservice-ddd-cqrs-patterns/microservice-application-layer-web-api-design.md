---
title: Progettazione del livello dell'applicazione di microservizi e dell'API Web
description: Architettura dei microservizi .NET per le applicazioni .NET in contenitori | Progettazione del livello dell'applicazione di microservizi e dell'API Web
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/12/2017
ms.openlocfilehash: a8c03f99accf75f60fe6c21a0f09f304214b4a6c
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50194111"
---
# <a name="designing-the-microservice-application-layer-and-web-api"></a>Progettazione del livello dell'applicazione di microservizi e dell'API Web

## <a name="using-solid-principles-and-dependency-injection"></a>Uso dei principi SOLID e dell'inserimento delle dipendenze

I principi SOLID sono tecniche fondamentali da usare nelle applicazioni cruciali moderne, ad esempio lo sviluppo di un microservizio con schemi progettazione basata su domini. SOLID è un acronimo che raggruppa cinque principi fondamentali:

-   SRP (Single Responsibility Principle, principio di singola responsabilità)

-   OCP (Open/Closed Principle, principio aperto/chiuso)

-   LSP (Liskov Substitution Principle, principio di sostituzione di Liskov)

-   Principio di segregazione delle interfacce (Interface Segregation Principle)

-   DIP (Dependency Inversion Principle, principio di inversione delle dipendenze)

SOLID si riferisce soprattutto alla progettazione dei livelli interni dell'applicazione o del microservizio e alla separazione delle reciproche dipendenze. Non è relativo al dominio, ma alla progettazione tecnica dell'applicazione. L'ultimo principio, quello dell'inversione delle dipendenze, consente di disaccoppiare il livello infrastruttura dagli altri livelli e permette quindi una migliore implementazione disaccoppiata dei livelli di progettazione basata su domini.

L'inserimento delle dipendenze è un modo per implementare il principio di inversione delle dipendenze. È una tecnica per ottenere un regime di controllo libero tra gli oggetti e le relative dipendenze. Invece di creare direttamente un'istanza dei collaboratori o usare riferimenti statici, gli oggetti necessari a una classe per eseguire le azioni vengono forniti alla (o "inseriti nella") classe. Nella maggior parte dei casi le classi dichiarano le dipendenze tramite il costruttore consentendo di seguire il principio delle dipendenze esplicite. L'inserimento delle dipendenze si basa in genere su contenitori a inversione del controllo (IoC, Inversion of Control). ASP.NET Core fornisce un semplice contenitore IoC predefinito, ma è anche possibile usare il contenitore IoC preferito, ad esempio Autofac o Ninject.

Se si seguono i principi SOLID, le classi tenderanno a essere piccole, con refactoring corretto e facili da testare. Ma come sapere se nelle classi vengono inserite troppe dipendenze? Se si usa l'inserimento delle dipendenze tramite il costruttore, sarà possibile determinarlo con facilità, semplicemente esaminando il numero di parametri del costruttore. Se le dipendenze sono troppe, ciò è in genere una prova (un [code smell](https://deviq.com/code-smells/)) che la classe sta provando a eseguire troppe operazioni e probabilmente sta violando il principio di singola responsabilità.

Per illustrare SOLID in dettaglio, servirebbe un'altra guida. Questa guida presuppone quindi che si abbia solo una conoscenza di base di questi argomenti.

#### <a name="additional-resources"></a>Risorse aggiuntive

-   **SOLID: Fundamental OOP Principles (SOLID: principi OOP fondamentali)**
    [*https://deviq.com/solid/*](https://deviq.com/solid/%20)

-   **Inversion of Control Containers and the Dependency Injection Pattern (Contenitori di inversione del controllo e modello di inserimento delle dipendenze)**
    [*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)

-   **Steve Smith. New is Glue**
    [*https://ardalis.com/new-is-glue*](https://ardalis.com/new-is-glue)


>[!div class="step-by-step"]
[Precedente](nosql-database-persistence-infrastructure.md)
[Successivo](microservice-application-layer-implementation-web-api.md)
