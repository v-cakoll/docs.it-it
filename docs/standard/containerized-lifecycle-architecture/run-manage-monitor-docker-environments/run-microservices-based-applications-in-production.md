---
title: Eseguire applicazioni basate su microservizi composte e negli ambienti di produzione
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 0d7611d07c9995984269e3f7b071154d9b861367
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2018
---
# <a name="run-composed-and-microservices-based-applications-in-production-environments"></a>Eseguire applicazioni basate su microservizi composte e negli ambienti di produzione

Applicazioni composte da più microservizi devono essere distribuiti in cluster di orchestrator per semplificare la complessità della distribuzione e renderlo utilizzabile dal punto di vista dell'IT. Senza un cluster di orchestrator, sarebbe molto difficile da distribuire e un'applicazione complessa microservizi scalare in orizzontale.

## <a name="introduction-to-orchestrators-schedulers-and-container-clusters"></a>Introduzione a orchestrators, le utilità di pianificazione e i cluster di contenitore

È stata introdotta in precedenza in questo e-book, *cluster* e *le utilità di pianificazione* come parte della discussione sull'architettura software e lo sviluppo. Esempi di cluster Docker sono Docker Swarm e Mesosphere Datacenter del sistema operativo (controller di dominio/OS). Entrambi questi è possibile eseguire come parte dell'infrastruttura fornito dal servizio di contenitore di Microsoft Azure.

Quando le applicazioni vengono scalate orizzontalmente tra più sistemi host, la possibilità di gestire ogni sistema host e astrarre la complessità della piattaforma sottostante diventa interessante. Che è esattamente cosa fornisce orchestrators e utilità di pianificazione. Diamo un'occhiata breve qui:

-   **Utilità di pianificazione * * * *"Pianificazione" si intende la possibilità per un amministratore caricare un file del servizio in un sistema host che consente di stabilire come eseguire un contenitore specifico. Avvio di contenitori in un cluster di Docker tende a essere noto come pianificazione. Sebbene la pianificazione si riferisce all'atto specifico di caricare la definizione del servizio, nel senso più generale, le utilità di pianificazione sono responsabili per l'associazione nel sistema init un host per gestire i servizi in qualsiasi capacità necessita.

Un'utilità di pianificazione di cluster con più obiettivi: utilizzando in modo efficiente le risorse del cluster, l'utilizzo di vincoli di posizionamento fornito dall'utente, la programmazione di applicazioni rapidamente lasciarli non in uno stato in sospeso, con una certa "equità", viene affidabile agli errori, e essere sempre disponibile.

-   **Orchestrazione * * * *piattaforme estendono le funzionalità di gestione del ciclo di vita a carichi di lavoro complessi e multicontainer distribuite in un cluster di host. : L'infrastruttura host, utilizzando strumenti di orchestrazione consentire agli utenti di gestire l'intero cluster come destinazione una singola distribuzione.

Il processo di orchestrazione implica strumenti e una piattaforma in grado di automatizzare tutti gli aspetti della gestione delle applicazioni dalla posizione iniziale o di distribuzione per ogni contenitore. lo spostamento di contenitori in host diversi a seconda dell'host o per l'integrità delle prestazioni. controllo delle versioni e in sequenza gli aggiornamenti e le funzioni che supportano il ridimensionamento e il failover; monitoraggio dello stato e molto altro ancora.

Orchestrazione si intende che fa riferimento al contenitore pianificazione, la gestione di cluster e probabilmente il provisioning di altri host.

Le funzionalità fornite da orchestrators e utilità di pianificazione sono molto complesse da sviluppare e creare da zero e pertanto è in genere si desidera rendere l'uso di soluzioni di orchestrazione offerti dai fornitori.


>[!div class="step-by-step"]
[Precedente] [Avanti] (gestire-produzione-docker-environments.md) (index.md)
