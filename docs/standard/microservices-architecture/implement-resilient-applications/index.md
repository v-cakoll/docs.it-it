---
title: Implementazione di applicazioni resilienti
description: Architettura di microservizi .NET per le applicazioni .NET incluse in contenitori | Implementazione di applicazioni resilienti
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: a6fc2f4c963d857be06e194468e2f8514437dd1d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-resilient-applications"></a>Implementazione di applicazioni resilienti

*Le applicazioni basate su microservizi e cloud devono essere in grado di gestire gli errori parziali che sicuramente si verificheranno. È necessario progettare l'applicazione in modo che sia resiliente a questi errori parziali.*

La resilienza è la capacità di correggere gli errori e continuare a funzionare. Non significa evitare gli errori, ma accettare il fatto che si verificheranno e trovare una modalità di gestione degli errori che eviti tempi di inattività o perdita di dati. L'obiettivo della resilienza è riportare l'applicazione in uno stato pienamente operativo dopo un errore.

È piuttosto difficoltoso progettare e distribuire un'applicazione basata su microservizi. Ma è anche necessario mantenere l'applicazione in esecuzione in un ambiente in cui è certo che si verifichi un determinato tipo di errori. Pertanto, l'applicazione deve essere resiliente. Deve essere progettata per gestire errori parziali, ad esempio interruzioni della rete o arresti anomali di nodi o macchine virtuali nel cloud. Anche lo spostamento di microservizi (contenitori) in un nodo diverso all'interno di un cluster può causare brevi errori intermittenti nell'applicazione.

I diversi componenti singoli dell'applicazione devono inoltre incorporare le funzionalità di monitoraggio dell'integrità. Seguendo le indicazioni riportate in questo capitolo, è possibile creare un'applicazione in grado di funzionare senza problemi malgrado tempi di inattività temporanei o le normali interruzioni che si verificano nelle distribuzioni complesse e basate su cloud.


>[!div class="step-by-step"]
[Precedente] (../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md) [Successivo] (handle-partial-failure.md)
