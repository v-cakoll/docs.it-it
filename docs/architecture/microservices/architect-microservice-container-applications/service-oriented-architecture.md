---
title: Architettura orientata ai servizi
description: Informazioni sulle differenze fondamentali tra microservizi e architettura orientata ai servizi.
ms.date: 09/20/2018
ms.openlocfilehash: 84786539fbac0e8b38a81a2580232474774cd355
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "68674928"
---
# <a name="service-oriented-architecture"></a>Architettura orientata ai servizi

Architettura orientata ai servizi è un termine molto usato che può avere significati diversi a seconda delle persone. In generale, architettura orientata ai servizi significa strutturare l'applicazione scomponendola in più servizio (comunemente servizi HTTP) che possono essere classificati in diversi tipi, come sottosistemi o livelli.

Tali servizi possono ora essere distribuiti come contenitori Docker per risolvere alcuni problemi di distribuzione, poiché tutte le dipendenze sono incluse nell'immagine del contenitore. Se, tuttavia, è necessario ridimensionare le applicazioni con architettura orientata ai servizi e la distribuzione è basata su host Docker singoli, possono verificarsi problemi di scalabilità e disponibilità. In questo caso, può essere utile usare il software di clustering Docker o un agente di orchestrazione, come illustrato nelle sezioni successive in cui vengono descritti gli approcci di distribuzione per i microservizi.

I contenitori Docker sono utili (ma non necessari) sia per le architetture orientate ai servizi tradizionali sia per le architetture di microservizi più avanzate.

I microservizi derivano dall'architettura orientata ai servizi, ma quest'ultima è diversa dall'architettura di microservizi. I broker centralizzati di grandi dimensioni, gli agenti di orchestrazione centralizzati a livello dell'organizzazione e il [bus di servizio aziendale](https://en.wikipedia.org/wiki/Enterprise_service_bus) (ESB, Enterprise Service Bus) sono funzionalità tipiche dell'architettura orientata ai servizi. Ma nella maggior parte dei casi, sono considerate come antipattern nella community dei microservizi. Alcuni infatti sostengono che "l'architettura dei microservizi è un'architettura orientata ai servizi progettata correttamente".

Questa guida fa riferimento ai microservizi, in quanto l'approccio dell'architettura orientato ai servizi è meno rigoroso rispetto ai requisiti e alle tecniche usati in un'architettura di microservizi. Se si è in grado di creare un'applicazione basata su microservizi, si riuscirà anche a creare una più semplice applicazione orientata ai servizi.

>[!div class="step-by-step"]
>[Successivo](docker-application-state-data.md)
>[precedente](microservices-architecture.md)
