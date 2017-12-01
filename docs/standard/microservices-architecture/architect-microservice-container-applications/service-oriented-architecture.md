---
title: Architettura orientata ai servizi
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Architettura orientata ai servizi
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 970ff86c77100077d4c7710c0a697d1745d35819
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="service-oriented-architecture"></a>Architettura orientata ai servizi 

Architettura orientata ai servizi (SOA) è un termine eccessivo e mira diversi significati a seconda degli utenti. Ma come denominatore comune, significa che è strutturare l'applicazione scomponendo in più servizi (più di frequente, come i servizi HTTP) che possono essere classificati come tipi diversi, ad esempio i sottosistemi o livelli di SOA.

Tali servizi possono ora essere distribuiti come contenitori di Docker, che risolve i problemi di distribuzione, poiché tutte le dipendenze sono inclusi nell'immagine contenitore. Tuttavia, quando è necessario applicare la scalabilità verticale applicazioni SOA, potrebbe essere la scalabilità e problemi di disponibilità, se si distribuisce in base a singolo host Docker. Si tratta in Docker software di clustering o agente di orchestrazione consentirà out, come illustrato nelle sezioni successive in cui vengono descritti gli approcci di distribuzione per microservizi.

I contenitori di docker sono utili, ma non obbligatorio, per le architetture orientate ai servizi tradizionali e le architetture di microservizi più avanzate.

Microservizi derivano da SOA, ma è diversa dall'architettura di microservizi SOA. Funzionalità quali grande Broker centrale, orchestrators centrale a livello di organizzazione e [Enterprise Service Bus (ESB)](https://en.wikipedia.org/wiki/Enterprise_service_bus) sono tipici di SOA. Ma nella maggior parte dei casi, si tratta di anti-pattern della community di microservizio. Infatti, alcuni utenti sostengono che "l'architettura del microservizio è SOA eseguita right".

Questa guida è incentrata su microservizi, poiché un approccio SOA è meno rigorosa rispetto i requisiti e le tecniche utilizzate in un'architettura microservizio. Se si conosce come compilare un'applicazione basata su microservizio, è inoltre necessario conoscere come compilare un'applicazione orientata ai servizi più semplice.




>[!div class="step-by-step"]
[Precedente] (docker-applicazione-stato-data.md) [Avanti] (microservizi architecture.md)
