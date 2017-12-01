---
title: Eseguire applicazioni basate su microservizi composte e negli ambienti di produzione
description: Ciclo di vita dell'applicazione nei contenitori Docker con strumenti e piattaforma Microsoft
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: e7a2788098aa731699cbb201c7177e7578907673
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="run-composed-and-microservices-based-applications-in-production-environments"></a>Eseguire applicazioni basate su microservizi composte e negli ambienti di produzione

Applicazioni composte da più microservizi devono essere distribuiti in cluster di orchestrator per semplificare la complessità della distribuzione e renderlo utilizzabile dal punto di vista dell'IT. Senza un cluster di orchestrator, sarebbe molto difficile da distribuire e un'applicazione complessa microservizi scalare in orizzontale.

## <a name="introduction-to-orchestrators-schedulers-and-container-clusters"></a>Introduzione a orchestrators, le utilità di pianificazione e i cluster di contenitore

È stata introdotta in precedenza in questo e-book, *cluster* e *le utilità di pianificazione* come parte della discussione sull'architettura software e lo sviluppo. Esempi di cluster Docker sono Docker Swarm e Mesosphere Datacenter del sistema operativo (controller di dominio/OS). Entrambi questi è possibile eseguire come parte dell'infrastruttura fornito dal servizio di contenitore di Microsoft Azure.

Quando le applicazioni vengono scalate orizzontalmente tra più sistemi host, la possibilità di gestire ogni sistema host e astrarre la complessità della piattaforma sottostante diventa interessante. Che è esattamente cosa fornisce orchestrators e utilità di pianificazione. Diamo un'occhiata breve qui:

-   **Utilità di pianificazione*** *"Pianificazione" si intende la possibilità che un amministratore di caricare un file di servizio in un sistema host che definisce le modalità di esecuzione di un contenitore specifico. Avvio di contenitori in un cluster di Docker tende a essere noto come pianificazione. Sebbene la pianificazione si riferisce all'atto specifico di caricare la definizione del servizio, nel senso più generale, le utilità di pianificazione sono responsabili per l'associazione nel sistema init un host per gestire i servizi in qualsiasi capacità necessita.

Un'utilità di pianificazione di cluster con più obiettivi: utilizzando in modo efficiente le risorse del cluster, l'utilizzo di vincoli di posizionamento fornito dall'utente, la programmazione di applicazioni rapidamente lasciarli non in uno stato in sospeso, con una certa "equità", viene affidabile agli errori, e essere sempre disponibile.

-   **Orchestrazione*** *piattaforme estendono la funzionalità di gestione del ciclo di vita a carichi di lavoro complessi e multicontainer distribuite in un cluster di host. : L'infrastruttura host, utilizzando strumenti di orchestrazione consentire agli utenti di gestire l'intero cluster come destinazione una singola distribuzione.

Il processo di orchestrazione implica strumenti e una piattaforma in grado di automatizzare tutti gli aspetti della gestione delle applicazioni dalla posizione iniziale o di distribuzione per ogni contenitore. lo spostamento di contenitori in host diversi a seconda dell'host o per l'integrità delle prestazioni. controllo delle versioni e in sequenza gli aggiornamenti e le funzioni che supportano il ridimensionamento e il failover; monitoraggio dello stato e molto altro ancora.

Orchestrazione si intende che fa riferimento al contenitore pianificazione, la gestione di cluster e probabilmente il provisioning di altri host.

Le funzionalità fornite da orchestrators e utilità di pianificazione sono molto complesse da sviluppare e creare da zero e pertanto è in genere si desidera rendere l'uso di soluzioni di orchestrazione offerti dai fornitori.


>[!div class="step-by-step"]
[Precedente] [Avanti] (gestire-produzione-docker-environments.md) (index.md)
