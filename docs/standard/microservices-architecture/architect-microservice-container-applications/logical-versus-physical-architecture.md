---
title: Architettura logica e architettura fisica
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Architettura logica e architettura fisica
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 635774a8fcd0cf1c0ede6a73c604071f538a37fd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="logical-architecture-versus-physical-architecture"></a>Architettura logica e architettura fisica

È utile a questo punto arrestare e discutere la distinzione tra l'architettura logica e architettura fisica e come si applica alla progettazione di applicazioni basate su microservizio.

Per iniziare, compilazione microservizi non richiede l'uso di qualsiasi tecnologia specifica. Ad esempio, i contenitori di Docker non sono obbligatori per creare un'architettura basata su microservizio. Tali microservizi potrebbero inoltre essere eseguiti come processi normali. Microservizi sono un'architettura logica.

Inoltre, anche quando un microservizio potrebbe essere implementata fisicamente come un singolo servizio, un processo o un contenitore (per semplicità, che è l'approccio adottato nella versione iniziale di [eShopOnContainers](http://aka.ms/MicroservicesArchitecture)), questa analogia Business microservizio e fisica del servizio o del contenitore non è necessariamente necessario in tutti i casi quando si compila un'applicazione di grande e complessa, costituita da molte decine o addirittura centinaia di servizi.

Questa opzione è quando sussiste una differenza tra l'architettura logica e architettura fisica di un'applicazione. L'architettura logica e i limiti di logici di un sistema non sono associati uno a uno per l'architettura fisica o di distribuzione. Può verificarsi, ma spesso non.

Anche se potrebbe aver identificato determinati microservizi business o contesti delimitata, non significa che è sempre il modo migliore per la relativa implementazione mediante la creazione di un singolo servizio (ad esempio un'API Web ASP.NET) o un singolo contenitore Docker per ogni microservizio di business. Con una regola che indica che ogni microservizio business deve essere implementato usando un singolo servizio o contenitore è troppo rigido.

Pertanto, un business microservizio o il contesto limitato è un'architettura logica che potrebbe coincidono (o non) con l'architettura fisica. L'aspetto importante è che un business microservizio o il contesto delimitata deve essere autonomo, consentendo di codice e lo stato venga in modo indipendente con controllo delle versioni, distribuite e ridimensionata.

Come illustrato nella figura 4-8, microservizio di business il catalogo potrebbe essere composti da più servizi o processi. Può trattarsi di più servizi API Web ASP.NET o qualsiasi altro tipo di servizi tramite HTTP o qualsiasi altro protocollo. Ancora più importante, i servizi può condividere gli stessi dati, purché questi servizi sono coesivi rispetto alla stesso dominio di business.

![](./media/image8.png)

**Figura 4-8**. Business microservizio con diversi servizi fisici

Nell'esempio i servizi condividono lo stesso modello di dati poiché il servizio Web API ha come destinazione gli stessi dati il servizio di ricerca. In tal caso, nell'implementazione fisica del microservizio di business, si divide tale funzionalità in modo è possibile scalare ognuno di tali servizi interni verso l'alto o verso il basso in base alle esigenze. Forse il servizio Web API deve in genere più istanze, il servizio di ricerca o viceversa.)

In breve, l'architettura logica di microservizi non è sempre necessario coincide con l'architettura di distribuzione fisica. In questa Guida, ogni volta che è importante tenere presente un microservizio, si intende un business o microservizio logica che può eseguire il mapping a uno o più servizi. Nella maggior parte dei casi, si tratterà di un singolo servizio, ma potrebbe essere maggiore di.


>[!div class="step-by-step"]
[Precedente] (dati-sovranità-per-microservice.md) [Avanti] (distributed-data-management.md)
