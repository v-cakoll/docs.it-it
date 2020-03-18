---
title: Implementare applicazioni resilienti
description: Informazioni sulla resilienza, un concetto fondamentale in un'architettura di microservizi. È necessario sapere come gestire gli errori temporanei in modo normale quando si verificano.
ms.date: 01/30/2020
ms.openlocfilehash: 46276a6b9b36a494bfae657275692ca9d5554d86
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78847232"
---
# <a name="implement-resilient-applications"></a>Implementare applicazioni resilienti

*Le applicazioni basate su microservizi e cloud devono accettare gli errori parziali che si verificheranno certamente alla fine. È necessario progettare l'applicazione in modo che sia resiliente a tali errori parziali.*

La resilienza è la capacità di recupero da errori che consente un funzionamento continuativo. Non significa evitare gli errori, ma accettare il fatto che si verificheranno e trovare una modalità di gestione degli errori che eviti tempi di inattività o perdita di dati. L'obiettivo della resilienza è riportare l'applicazione in uno stato pienamente operativo dopo un errore.

È piuttosto difficoltoso progettare e distribuire un'applicazione basata su microservizi. Ma è anche necessario mantenere l'applicazione in esecuzione in un ambiente in cui è certo che si verifichi un determinato tipo di errori. Pertanto, l'applicazione deve essere resiliente. Deve essere progettata per gestire errori parziali, ad esempio interruzioni della rete o arresti anomali di nodi o macchine virtuali nel cloud. Anche lo spostamento di microservizi (contenitori) in un nodo diverso all'interno di un cluster può causare brevi errori intermittenti nell'applicazione.

I diversi componenti singoli dell'applicazione devono inoltre incorporare le funzionalità di monitoraggio dell'integrità. Seguendo le indicazioni riportate in questo capitolo, è possibile creare un'applicazione in grado di funzionare senza problemi malgrado tempi di inattività temporanei o le normali interruzioni che si verificano nelle distribuzioni complesse e basate su cloud.

>[!IMPORTANT]
> eShopOnContainer utilizzava la [libreria Polly](http://www.thepollyproject.org/) per implementare la resilienza usando [i client tipizzato](./use-httpclientfactory-to-implement-resilient-http-requests.md) fino alla versione 3.0.0.
>
> A partire dalla versione 3.0.0, la resilienza delle chiamate HTTP viene implementata utilizzando una [rete Linkerd](https://linkerd.io/), che gestisce i tentativi in modo trasparente e configurabile, all'interno di un cluster Kubernetes, senza dover gestire tali problemi nel codice.
>
> La libreria Polly viene comunque utilizzata per aggiungere resilienza alle connessioni di database, specialmente durante l'avvio dei servizi.

>[!WARNING]
> Tutti gli esempi di codice in questa sezione erano validi prima di utilizzare Linkerd e non vengono aggiornati per riflettere il codice effettivo corrente. Quindi hanno senso nel contesto di questa sezione.

>[!div class="step-by-step"]
>[Successivo](../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)
>[precedente](handle-partial-failure.md)
