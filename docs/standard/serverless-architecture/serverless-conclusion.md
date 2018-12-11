---
title: Considerazioni principali - App senza server
description: Serverless fornisce numerosi vantaggi e presenta difficoltà specifiche. Riepilogo delle considerazioni principali da questa Guida.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 6f4951dc85f739b92e56e84d0bd0262166181bd4
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128843"
---
# <a name="conclusion"></a>Conclusione

Le seguenti considerazioni principali sono le conclusioni più importanti da questa Guida.

**Vantaggi dell'utilizzo senza server.** Soluzioni senza server offrono vantaggi significativi in termini di risparmio sui costi perché senza server viene implementato in un modello con pagamento a consumo. Serverless rende possibile ridimensionare, testare e distribuire i singoli componenti dell'applicazione in modo indipendente. Un'infrastruttura senza server si rivelano particolarmente adatte per implementare architetture di microservizi e si integra completamente in una pipeline DevOps.

**Il codice come un'unità di distribuzione.** Serverless astrae l'hardware, sistema operativo e runtime dall'applicazione. Senza server consente di concentrarsi sulla logica di business nel codice come unità di distribuzione.

**Trigger e associazioni.** Serverless semplifica l'integrazione con archiviazione, le API e altre risorse cloud. Funzioni di Azure consente l'esecuzione di codice e le associazioni per interagire con le risorse di trigger.

**Microservizi.** L'architettura di microservizi sta diventando l'approccio consigliato per applicazioni mission-critical distribuite di grandi dimensioni o complesse basate su più sottosistemi indipendenti sotto forma di servizi autonomi. In un'architettura basata su microservizi, l'applicazione viene compilata come una raccolta di servizi che possono essere sviluppati, testati, con controllo delle versioni, distribuiti e ridimensionati in modo indipendente. Senza server è un'architettura particolarmente adatta per la creazione di questi servizi.

**Piattaforme senza server.** Senza server non riguarda solo il codice. Piattaforme che supportano le architetture senza server includono flussi di lavoro senza server e orchestrazione, di messaggistica senza server e servizi eventi e i database senza server.

**Sfide senza server.** Serverless introduce sfide relative allo sviluppo di applicazioni distribuite, ad esempio frammentato e modelli di dati indipendenti, resilienza, controllo delle versioni e individuazione del servizio. Un'infrastruttura senza server non può essere adatto a esecuzione prolungata processi o i componenti che traggono vantaggio da una maggiore accoppiamento.

**Senza server come uno strumento, non della casella degli strumenti.** Senza server è non sulla soluzione esclusiva all'architettura delle applicazioni. È uno strumento che può essere usato come parte di un'applicazione ibrida che può contenere livelli tradizionali, monolite back-end e i contenitori. Un'infrastruttura senza server possono essere usate per migliorare soluzioni esistenti e non è un approccio di tipo tutto o niente per lo sviluppo di applicazioni.

>[!div class="step-by-step"]
>[Precedente](serverless-business-scenarios.md)