---
title: Eseguire applicazioni composte e basate su microservizi in ambienti di produzione
description: Informazioni sui componenti chiave per l'esecuzione di applicazioni basate su contenitori in produzione
ms.date: 02/15/2019
ms.openlocfilehash: 69df3d39a00b91cbe59c96e5fcab841a60943bcc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "68672918"
---
# <a name="run-composed-and-microservices-based-applications-in-production-environments"></a>Eseguire applicazioni composte e basate su microservizi in ambienti di produzione

Per ridurre la complessità della distribuzione e renderla attuabile dal punto di vista IT, è necessario distribuire le applicazioni composte da più microservizi in cluster di agenti di orchestrazione. Senza un cluster di agenti di orchestrazione, la distribuzione e lo scale-out di un'applicazione di microservizi complessa risulterebbero difficili.

## <a name="introduction-to-orchestrators-schedulers-and-container-clusters"></a>Introduzione ad agenti di orchestrazione, utilità di pianificazione e cluster di contenitori

In questo e-book, i *cluster* e le *utilità di pianificazione* sono stati precedentemente introdotti nel contesto della discussione sull'architettura e sullo sviluppo di software. Kubernetes e Service Fabric sono esempi di cluster Docker. Entrambi questi agenti di orchestrazione possono essere eseguiti come parte dell'infrastruttura offerta dal servizio Microsoft Azure Kubernetes.

Durante lo scale-out delle applicazioni su più sistemi host, la possibilità di gestire ogni sistema host e astrarre la complessità della piattaforma sottostante diventa un aspetto interessante. Gli agenti di orchestrazione e le utilità di pianificazione offrono esattamente questo. Di seguito viene riportata una breve panoramica:

- **Utilità di pianificazione**.Per "pianificazione" si intende la capacità di un amministratore di caricare in un sistema host un file del servizio che stabilisce come eseguire uno specifico contenitore. L'avvio dei contenitori in un cluster Docker tende a essere noto come pianificazione. Anche se la pianificazione si riferisce all'atto specifico di caricare la definizione del servizio, in senso più generale, le utilità di pianificazione sono responsabili dell'azione di hook nel sistema di inizializzazione di un host per gestire i servizi nella capacità necessaria.

   L'utilità di pianificazione di un cluster ha molteplici obiettivi: uso efficiente delle risorse del cluster, uso dei vincoli di posizionamento specificati dall'utente, pianificazione rapida delle applicazioni in modo da non lasciarle in uno stato di sospensione, ma con un grado di "correttezza" e solidità rispetto agli errori e sempre disponibili.

- **Orchestratori**.Le piattaforme estendono le funzionalità di gestione del ciclo di vita a carichi di lavoro multi-contenitore complessi distribuiti in un cluster di host. Astraendo l'infrastruttura host, gli strumenti di orchestrazione consentono agli utenti di considerare l'intero cluster come una singola destinazione di distribuzione.

   Il processo di orchestrazione comporta l'uso di strumenti e di una piattaforma in grado di automatizzare tutti gli aspetti della gestione delle applicazioni, ad esempio il posizionamento iniziale o la distribuzione per contenitore, lo spostamento dei contenitori in host diversi a seconda dell'integrità o delle prestazioni del relativo host, il controllo delle versioni e l'implementazione di aggiornamenti e funzioni di monitoraggio dell'integrità che supportano la scalabilità e il failover e molto altro ancora.

   Orchestrazione è un termine generico che si riferisce alla pianificazione di contenitori, alla gestione dei cluster ed eventualmente al provisioning di altri host.

Lo sviluppo e la creazione da zero delle funzionalità offerte da agenti di orchestrazione e utilità di pianificazione sono attività complesse, quindi in genere si preferisce usare soluzioni di orchestrazione offerte dai fornitori.

>[!div class="step-by-step"]
>[Successivo](index.md)
>[precedente](manage-production-docker-environments.md)
