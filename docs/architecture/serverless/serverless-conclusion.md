---
title: Principali takeaway-app senza server
description: Il senza server offre molti vantaggi e presenta delle proprie esigenze. Riepilogo delle considerazioni principali di questa guida.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: ae9fc47bf07a7e28688942b856b4743ae7aadc36
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2019
ms.locfileid: "69577244"
---
# <a name="conclusion"></a>Conclusione

Di seguito sono riportate le considerazioni più importanti di questa guida.

**Vantaggi dell'utilizzo senza server.** Le soluzioni senza server offrono i vantaggi principali offerti dal risparmio sui costi, poiché l'implementazione senza server è implementata in un modello con pagamento in base al consumo. Senza server consente di ridimensionare, testare e distribuire i singoli componenti dell'applicazione in modo indipendente. Il server è particolarmente adatto per implementare architetture di microservizi e si integra completamente in una pipeline DevOps.

**Codice come unità di distribuzione.** Senza server, l'hardware, il sistema operativo e il runtime vengono estratti dall'applicazione. Senza server consente di concentrarsi sulla logica di business nel codice come unità di distribuzione.

**Trigger e associazioni.** L'integrazione senza server semplifica l'integrazione con archiviazione, API e altre risorse cloud. Funzioni di Azure fornisce trigger per eseguire codice e associazioni per interagire con le risorse.

**Microservizi.** L'architettura dei microservizi sta diventando l'approccio preferito per le applicazioni mission-critical distribuite e grandi o complesse basate su più sottosistemi indipendenti sotto forma di servizi autonomi. In un'architettura basata su microservizi, l'applicazione è compilata come una raccolta di servizi che possono essere sviluppati, testati, sottoposti a controllo delle versioni, distribuiti e ridimensionati in modo indipendente. Senza server è un'architettura particolarmente adatta per la creazione di questi servizi.

**Piattaforme senza server.** Il senza server non è solo il codice. Le piattaforme che supportano architetture senza server includono flussi di lavoro senza server e orchestrazioni, messaggistica senza server e servizi eventi e database senza server.

**Problemi senza server.** Senza server sono stati introdotti problemi correlati allo sviluppo di applicazioni distribuite, ad esempio modelli di dati frammentati e indipendenti, resilienza, controllo delle versioni e individuazione dei servizi. Il server non può essere particolarmente adatto ai processi o ai componenti con esecuzione prolungata che traggono vantaggio da un accoppiamento più rigido.

**Senza server come strumento, non come casella degli strumenti.** Senza server non è la soluzione esclusiva per l'architettura dell'applicazione. Si tratta di uno strumento che può essere utilizzato come parte di un'applicazione ibrida che può contenere livelli tradizionali, back-end monolitici e contenitori. Non è possibile usare senza server per migliorare le soluzioni esistenti e non è un approccio completamente o nulla allo sviluppo di applicazioni.

>[!div class="step-by-step"]
>[Precedente](serverless-business-scenarios.md)
