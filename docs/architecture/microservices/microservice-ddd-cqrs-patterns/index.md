---
title: Gestione della complessità aziendale in un microservizio con i modelli DDD e CQRS
description: Architettura di microservizi .NET per le applicazioni .NET incluse in contenitori | Informazioni su come gestire scenari aziendali complessi applicando i modelli DDD e CQRS
ms.date: 10/08/2018
ms.openlocfilehash: 88b105b68307c8587f877bb9ddf370e143d8539b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "73739846"
---
# <a name="tackle-business-complexity-in-a-microservice-with-ddd-and-cqrs-patterns"></a>Gestire la complessità aziendale in un microservizio con i modelli DDD e CQRS

*Progettare un modello di dominio per ogni microservizio o contesto vincolato che rispecchi le informazioni esistenti sul dominio aziendale.*

Questa sezione illustra i microservizi più avanzati implementabili quando è necessario gestire sottosistemi complessi o i microservizi derivati dalla conoscenza degli esperti del settore con regole business in continua evoluzione. I modelli di architettura usati in questa sezione si basano su approcci per la progettazione basata su domini (DDD) e la separazione di responsabilità per query e comandi (CQRS), come illustrato nella figura 7-1.

:::image type="complex" source="./media/index/internal-versus-external-architecture.png" alt-text="Diagramma che confronta modelli di architettura interni ed esterni.":::
Differenza tra l'architettura esterna (modelli di microservizio, gateway API, comunicazioni resilienti, pubblicazione/sottoscrizione e così via) e l'architettura interna (basata su dati/CRUD, modelli DDD, inserimento di dipendenze, librerie multiple e così via).
:::image-end:::

**Figura 7-1**. Architettura di microservizi esterna e modelli di architettura interna per ogni microservizio a confronto

Tuttavia, la maggior parte delle tecniche per microservizi basati sui dati, ad esempio come implementare un servizio API Web ASP.NET Core o come esporre metadati Swagger con Swashbuckle o NSwag, è anche applicabile ai microservizi più avanzati implementati internamente con modelli DDD. Questa sezione è un'estensione delle sezioni precedenti, poiché la maggior parte delle procedure illustrate prima si applicano anche qui o per qualsiasi tipo di microservizio.

Questa sezione fornisce innanzitutto informazioni dettagliate sui modelli CQRS semplificati usati nell'applicazione di riferimento eShopOnContainers. Successivamente, verrà fornita una panoramica delle tecniche DDD che consentono di individuare modelli comuni riutilizzabili nelle applicazioni.

DDD è un argomento vasto con un'ampia gamma di risorse di apprendimento. È possibile iniziare da pubblicazioni come [Domain-Driven Design](https://domainlanguage.com/ddd/) di Eric Evans e altro materiale di Vaughn Vernon, Jimmy Nilsson, Greg Young, Udi Dahan, Jimmy Bogard e molti altri esperti di DDD/CQRS. Ma la cosa più importante è tentare di apprendere come applicare le tecniche DDD da conversazioni, lavagne e sessioni di modellazione di dominio con esperti del dominio aziendale reale.

#### <a name="additional-resources"></a>Risorse aggiuntive

##### <a name="ddd-domain-driven-design"></a>Progettazione basata su domini (DDD)

- **Eric Evans.**  \ della lingua del dominio
  <https://domainlanguage.com/>

- **Martin Fowler. \ della progettazione basata su dominio**
  <https://martinfowler.com/tags/domain%20driven%20design.html>

- **Jimmy Bogard. Rafforzamento del dominio: un Nozioni di fondo** \
  <https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/>

##### <a name="ddd-books"></a>Pubblicazioni sulla progettazione DDD

- **Eric Evans. Progettazione basata su domini: affrontare la complessità nel cuore del software** \
  <https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/>

- **Eric Evans. Riferimento alla progettazione basata su dominio: definizioni e riepiloghi dei modelli** \
  <https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/>

- **Vaughn Vernon. Implementazione della progettazione basata su dominio** \
  <https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/>

- **Vaughn Vernon. Progettazione basata su dominio distillata** \
  <https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/>

- **Jimmy Nilsson. Applicazione di modelli e progettazione basati su dominio** \
  <https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/>

- **Cesar de la Torre. Guida all'architettura orientata ai domini a più livelli con .NET** \
  <https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/>

- **Abel Avram e Floyd Marinescu. Progettazione basata su domini \ rapidamente**
  <https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/>

- **Scott Millett, Nick Tune - Patterns, Principles, and Practices of Domain-Driven Design (Modelli, principi e procedure della progettazione basata su domini)**  \
  <http://www.wrox.com/WileyCDA/WroxTitle/Patterns-Principles-and-Practices-of-Domain-Driven-Design.productCd-1118714709.html>

##### <a name="ddd-training"></a>Training per la progettazione DDD

- **Julie Lerman e Steve Smith. Nozioni fondamentali sulla progettazione basata su dominio** \
  <https://bit.ly/PS-DDD>

>[!div class="step-by-step"]
>[Precedente](../multi-container-microservice-net-applications/implement-api-gateways-with-ocelot.md)
>[Successivo](apply-simplified-microservice-cqrs-ddd-patterns.md)
