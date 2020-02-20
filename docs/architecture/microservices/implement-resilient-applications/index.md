---
title: Implementare applicazioni resilienti
description: Informazioni sulla resilienza, un concetto fondamentale in un'architettura di microservizi. Quando si verificano, è necessario saper gestire correttamente gli errori temporanei.
ms.date: 01/30/2020
ms.openlocfilehash: ccdb2470c727ad4bd89c4e0634da8564b8010e63
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77502647"
---
# <a name="implement-resilient-applications"></a>Implementare applicazioni resilienti

*Il microservizio e le applicazioni basate sul cloud devono accettare gli errori parziali che probabilmente si verificheranno. È necessario progettare l'applicazione in modo che sia resiliente agli errori parziali.*

La resilienza è la capacità di correggere gli errori e continuare a funzionare. Non significa evitare gli errori, ma accettare il fatto che si verificheranno e trovare una modalità di gestione degli errori che eviti tempi di inattività o perdita di dati. L'obiettivo della resilienza è riportare l'applicazione in uno stato pienamente operativo dopo un errore.

È piuttosto difficoltoso progettare e distribuire un'applicazione basata su microservizi. Ma è anche necessario mantenere l'applicazione in esecuzione in un ambiente in cui è certo che si verifichi un determinato tipo di errori. Pertanto, l'applicazione deve essere resiliente. Deve essere progettata per gestire errori parziali, ad esempio interruzioni della rete o arresti anomali di nodi o macchine virtuali nel cloud. Anche lo spostamento di microservizi (contenitori) in un nodo diverso all'interno di un cluster può causare brevi errori intermittenti nell'applicazione.

I diversi componenti singoli dell'applicazione devono inoltre incorporare le funzionalità di monitoraggio dell'integrità. Seguendo le indicazioni riportate in questo capitolo, è possibile creare un'applicazione in grado di funzionare senza problemi malgrado tempi di inattività temporanei o le normali interruzioni che si verificano nelle distribuzioni complesse e basate su cloud.

>[!IMPORTANT]
> eShopOnContainer usa la [libreria Polly](http://www.thepollyproject.org/) per implementare la resilienza usando [client tipizzati](./use-httpclientfactory-to-implement-resilient-http-requests.md) fino alla versione 3.0.0.
>
> A partire dalla versione 3.0.0, la resilienza delle chiamate HTTP viene implementata usando una [mesh Linkerd](https://linkerd.io/), che gestisce i tentativi in modo trasparente e configurabile, all'interno di un cluster Kubernetes, senza dover gestire tali problematiche nel codice.
>
> La libreria Polly viene ancora usata per aggiungere la resilienza alle connessioni di database, in particolare durante l'avvio dei servizi.

>[!WARNING]
> Tutti gli esempi di codice in questa sezione sono validi prima di usare Linkerd e non vengono aggiornati per riflettere il codice effettivo corrente. Quindi hanno senso nel contesto di questa sezione.

>[!div class="step-by-step"]
>[Precedente](../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)
>[Successivo](handle-partial-failure.md)
