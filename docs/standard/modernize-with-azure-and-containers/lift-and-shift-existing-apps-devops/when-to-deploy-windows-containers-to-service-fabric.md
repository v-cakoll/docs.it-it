---
title: Quando distribuire i contenitori di Windows a Service Fabric
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Quando distribuire i contenitori di Windows a Service Fabric
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 162714e86d1c714deea5ab7af640b66be8f330bd
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="when-to-deploy-windows-containers-to-service-fabric"></a>Quando distribuire i contenitori di Windows a Service Fabric

Le applicazioni basate sui contenitori di Windows, rapidamente è necessario utilizzare le piattaforme che allontana ulteriormente da macchine virtuali IaaS. Per migliorare la scalabilità automatica e scalabilità elevate e per ottenere miglioramenti significativi in un'esperienza di gestione completa per le distribuzioni, aggiornamenti, controllo delle versioni, rollback e il monitoraggio dello stato. È possibile raggiungere questi obiettivi con orchestrator Azure Service Fabric, disponibile nel cloud di Microsoft Azure, ma anche in locale, o anche in un altro cloud.

Molte organizzazioni sono sollevamento e spostamento di applicazioni monolitiche esistenti per i contenitori per due motivi:

-   Riduzione dei costi, a causa di consolidamento e la rimozione dell'hardware esistente, o da applicazioni in esecuzione in una densità più elevata.

-   Un contratto di distribuzione coerente tra lo sviluppo e operazioni.

Utilizzare la riduzione dei costi è riconosciuto, ed è probabile che tutte le organizzazioni sono la ricerca di tale obiettivo. Distribuzione uniforme è più difficile da valutare, ma è ugualmente importante. Un contratto a distribuzione uniforme è indicato che gli sviluppatori possono scegliere di utilizzare la tecnologia e adeguato alle esigenze e il team operativo Ottiene un unico modo per distribuire e gestire applicazioni. Il presente contratto consente di attenuare il problema della presenza di gestire la complessità delle numerose tecnologie diverse operazioni o imporre agli sviluppatori di usare solo alcune delle tecnologie. Ogni applicazione è in pratica, contenitore in un'immagine di distribuzione autonomo.

Alcune organizzazioni continuerà modernizzazione aggiungendo microservizi (applicazioni ottimizzato su Cloud e cloud nativo). Molte organizzazioni terminerà qui (DevOps pronta). Come illustrato nella figura 4-8, queste organizzazioni non spostare architetture microservizi perché potrebbe non necessario. In ogni caso, sono già ottenere i vantaggi che utilizzando contenitori plus Service Fabric esperienza fornisce una gestione completa che include la distribuzione, viene aggiornato, il controllo delle versioni, rollback e il monitoraggio dello stato.

> ![Spostare un'applicazione di Service Fabric](./media/image8.png)
>
> **Figura 4-8.** Spostare un'applicazione di Service Fabric

Un approccio a Service Fabric chiave consiste nel riutilizzare il codice esistente e semplicemente sollevare e spostare. Pertanto, è possibile eseguire la migrazione di applicazioni .NET Framework corrente, usando i contenitori di Windows e distribuirli a Service Fabric. Sarà più semplice mantenere passare modernizzazione, infine, tramite l'aggiunta di nuovi microservizi.

Quando si confrontano Service Fabric per altri orchestrators, è importante evidenziare che Service Fabric è molto consolidato all'esecuzione dei servizi e applicazioni basate su Windows. Service Fabric è stato in esecuzione servizi basati su Windows e applicazioni, compresi i-1 a livello di importanza critica prodotti Microsoft, per gli anni. È stato agente di orchestrazione prima di disporre di disponibilità generale per i contenitori di Windows (maggio 2017). Altri contenitori, ad esempio Kubernetes, controller di dominio/OS e Docker Swarm, sono più maturi in Linux, ma meno avanzata di servizi dell'infrastruttura per applicazioni Windows e i contenitori di Windows.

L'obiettivo finale di Service Fabric è ridurre la complessità della compilazione di applicazioni utilizzando un approccio di microservizi. Si tratta in cui si desidera infine che per alcuni tipi di applicazioni, per evitare costosi riprogettazioni. È possibile iniziare quando necessario, deprecare i servizi, aggiungere nuovi servizi e le sviluppare l'applicazione con utilizzo cliente. Sappiamo che non esistono molti altri problemi che devono ancora essere risolti affinché microservizi più accessibile per gli sviluppatori. Se attualmente sono appena sollevamento e spostamento di un'applicazione con i contenitori di Windows, ma si sta pensando di aggiunta di microservizi basato sui contenitori in futuro, che è l'ideale Service Fabric.

>[!div class="step-by-step"]
[Precedente](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Successivo](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
