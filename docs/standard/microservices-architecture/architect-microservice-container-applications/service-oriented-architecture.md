---
title: Architettura orientata ai servizi
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Architettura orientata ai servizi
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 67560cc93b3d147be36a691af440bb78f2315557
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105005"
---
# <a name="service-oriented-architecture"></a>Architettura orientata ai servizi 

Architettura orientata ai servizi è un termine molto usato che può avere significati diversi a seconda delle persone. In generale, architettura orientata ai servizi significa strutturare l'applicazione scomponendola in più servizio (comunemente servizi HTTP) che possono essere classificati in diversi tipi, come sottosistemi o livelli.

Tali servizi possono ora essere distribuiti come contenitori Docker per risolvere alcuni problemi di distribuzione, poiché tutte le dipendenze sono incluse nell'immagine del contenitore. Tuttavia, se è necessario ridimensionare le applicazioni con architettura orientata ai servizi per aumentarne le prestazioni, è possibile riscontrare problematiche di scalabilità e disponibilità se la distribuzione è basata su host Docker singoli. In questo caso, è opportuno usare il software di clustering Docker o un agente di orchestrazione, come illustrato nelle sezioni successive dove vengono descritti gli approcci di distribuzione per i microservizi.

I contenitori Docker sono utili (ma non necessari) sia per le architetture orientate ai servizi tradizionali sia per le architetture di microservizi più avanzate.

I microservizi derivano dall'architettura orientata ai servizi, ma quest'ultima è diversa dall'architettura di microservizi. I broker centralizzati di grandi dimensioni, gli agenti di orchestrazione centralizzati a livello dell'organizzazione e il [bus di servizio aziendale](https://en.wikipedia.org/wiki/Enterprise_service_bus) (ESB, Enterprise Service Bus) sono funzionalità tipiche dell'architettura orientata ai servizi. Ma nella maggior parte dei casi, sono considerate come antipattern nella community dei microservizi. Infatti, alcuni sostengono che l'"architettura di microservizi non è altro che un'architettura orientata ai servizi".

Questa guida fa riferimento ai microservizi, in quanto l'approccio dell'architettura orientato ai servizi è meno rigoroso rispetto ai requisiti e alle tecniche usati in un'architettura di microservizi. Se si è in grado di creare un'applicazione basata su microservizi, si riuscirà anche a creare una più semplice applicazione orientata ai servizi.




>[!div class="step-by-step"]
[Precedente](docker-application-state-data.md)
[Successivo](microservices-architecture.md)
