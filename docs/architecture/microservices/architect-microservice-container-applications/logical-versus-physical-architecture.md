---
title: Architettura logica e architettura fisica
description: Informazioni sulle differenze tra architetture logiche e architetture fisiche.
ms.date: 09/20/2018
ms.openlocfilehash: 8d1bfca190eb9b18d46625fa4afdec963eb07054
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "71834406"
---
# <a name="logical-architecture-versus-physical-architecture"></a>Architettura logica e architettura fisica

A questo punto, è utile fermarsi per esaminare la distinzione tra architettura logica e architettura fisica e valutare come si applica alla progettazione di applicazioni basate su microservizi.

Per iniziare, la creazione di microservizi non richiede l'uso di alcuna tecnologia specifica. Ad esempio, non è obbligatorio usare contenitori Docker per creare un'architettura basata su microservizi. I microservizi possono anche essere eseguiti come processi normali. I microservizi sono un'architettura logica.

Inoltre, anche quando è possibile implementare un microservizio fisicamente come un singolo servizio, processo o contenitore (per semplicità, questo è l'approccio adottato per la versione iniziale di [eShopOnContainers](https://aka.ms/MicroservicesArchitecture)), questa parità tra microservizi aziendali e contenitori o servizi fisici non è necessariamente richiesta in tutti i casi quando si crea un'applicazione complessa di grandi dimensioni costituita da decine o centinaia di servizi.

Qui sta la differenza tra l'architettura logica e l'architettura fisica di un'applicazione. L'architettura logica e i limiti logici di un sistema non presentano necessariamente un mapping di uno-a-uno rispetto all'architettura di distribuzione o fisica. Può verificarsi, ma spesso non accade.

Sebbene possano essere stati identificati alcuni microservizi aziendali o contesti delimitati, questo non significa che il miglior modo di implementarli sia sempre costituito dalla creazione di un singolo servizio, ad esempio un'API Web ASP.NET, o un singolo contenitore Docker per ogni microservizio aziendale. Una regola che prevede che ogni microservizio aziendale debba essere implementato con un singolo servizio o contenitore è troppo rigida.

Di conseguenza, un microservizio aziendale o un contesto delimitato è un'architettura logica che potrebbe coincidere (oppure no) con l'architettura fisica. Il punto importante è che un microservizio aziendale o un contesto delimitato deve essere autonomo e consentire al codice e allo stato il controllo delle versioni, la distribuzione e il ridimensionamento indipendenti.

Come mostrato nella figura 4-8, il microservizio aziendale del catalogo può essere composto da numerosi servizi o processi. Questi possono essere costituiti da più servizi API Web ASP.NET o da altre tipologie di servizi che usano HTTP o altri protocolli. Inoltre, i servizi possono condividere gli stessi dati, purché siano coesi rispetto allo stesso dominio aziendale.

![Diagramma del microservizio aziendale del catalogo con server fisici.](./media/logical-versus-physical-architecture/multiple-physical-services.png)

**Figura 4-8**. Microservizio aziendale con numerosi servizi fisici

I servizi nell'esempio condividono lo stesso modello di dati perché il servizio API Web usa gli stessi dati del servizio di ricerca. Quindi, nell'implementazione fisica del microservizio aziendale si divide questa funzionalità per poter ridimensionare ogni servizio interno in base alle esigenze. Nella maggior parte dei casi il servizio API Web potrebbe richiedere un maggior numero di istanze rispetto al servizio di ricerca o viceversa.

In breve, l'architettura logica dei microservizi non deve sempre coincidere con l'architettura di distribuzione fisica. In questa guida ogni volta che viene citato un microservizio si intente un microservizio logico o aziendale che può essere mappato a uno o più servizi (fisici). Nella maggior parte dei casi, si tratterà di un singolo servizio, ma potrebbero anche essere più servizi.

>[!div class="step-by-step"]
>[Successivo](data-sovereignty-per-microservice.md)
>[precedente](distributed-data-management.md)
