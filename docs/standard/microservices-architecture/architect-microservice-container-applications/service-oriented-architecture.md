---
title: Architettura orientata ai servizi
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Architettura orientata ai servizi
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6a5f0f53f4208c9944adea33fe1aa3f35fed81ab
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="service-oriented-architecture"></a>Architettura orientata ai servizi 

Architettura orientata ai servizi è un termine molto usato che può avere significati diversi a seconda delle persone. In generale, architettura orientata ai servizi significa strutturare l'applicazione scomponendola in più servizio (comunemente servizi HTTP) che possono essere classificati in diversi tipi, come sottosistemi o livelli.

Tali servizi possono ora essere distribuiti come contenitori Docker per risolvere alcuni problemi di distribuzione, poiché tutte le dipendenze sono incluse nell'immagine del contenitore. Tuttavia, se è necessario ridimensionare le applicazioni con architettura orientata ai servizi per aumentarne le prestazioni, è possibile riscontrare problematiche di scalabilità e disponibilità se la distribuzione è basata su host Docker singoli. In questo caso, è opportuno usare il software di clustering Docker o un agente di orchestrazione, come illustrato nelle sezioni successive dove vengono descritti gli approcci di distribuzione per i microservizi.

I contenitori Docker sono utili (ma non necessari) sia per le architetture orientate ai servizi tradizionali sia per le architetture di microservizi più avanzate.

I microservizi derivano dall'architettura orientata ai servizi, ma quest'ultima è diversa dall'architettura di microservizi. I broker centralizzati di grandi dimensioni, gli agenti di orchestrazione centralizzati a livello dell'organizzazione e il [bus di servizio aziendale](https://en.wikipedia.org/wiki/Enterprise_service_bus) (ESB, Enterprise Service Bus) sono funzionalità tipiche dell'architettura orientata ai servizi. Ma nella maggior parte dei casi, sono considerate come antipattern nella community dei microservizi. Infatti, alcuni sostengono che l'"architettura di microservizi non è altro che un'architettura orientata ai servizi".

Questa guida fa riferimento ai microservizi, in quanto l'approccio dell'architettura orientato ai servizi è meno rigoroso rispetto ai requisiti e alle tecniche usati in un'architettura di microservizi. Se si è in grado di creare un'applicazione basata su microservizi, si riuscirà anche a creare una più semplice applicazione orientata ai servizi.




>[!div class="step-by-step"]
[Indietro] (docker-application-state-data.md) [Avanti] (microservices-architecture.md)
