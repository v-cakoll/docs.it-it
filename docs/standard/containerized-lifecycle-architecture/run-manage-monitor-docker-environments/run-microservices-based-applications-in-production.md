---
title: Eseguire applicazioni basate su microservizi composte e negli ambienti di produzione
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: b4192ff1d67a3f70bb5eeb9a36245cfd35bafb53
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105631"
---
# <a name="run-composed-and-microservices-based-applications-in-production-environments"></a>Eseguire applicazioni basate su microservizi composte e negli ambienti di produzione

Le applicazioni composte da più microservizi devono essere distribuiti in cluster di orchestrator per semplificare la complessità della distribuzione e renderlo utilizzabile dal punto di vista dell'IT. Senza un cluster con orchestrator, sarebbe molto difficile da distribuire e un'applicazione di microservizi complesso con scalabilità orizzontale.

## <a name="introduction-to-orchestrators-schedulers-and-container-clusters"></a>Introduzione a orchestrators, le utilità di pianificazione e contenitore cluster

È stata introdotta in precedenza in questo e-book *cluster* e *utilità di pianificazione* come parte della discussione sull'architettura software e lo sviluppo. Esempi di cluster di Docker sono Docker Swarm e Mesosphere Datacenter del sistema operativo (controller di dominio/OS). Entrambe queste eseguibili come parte dell'infrastruttura fornito dal servizio di contenitore di Microsoft Azure.

Quando le applicazioni vengono scalate orizzontalmente tra più sistemi host, la possibilità di gestire ogni sistema host e astrarre la complessità della piattaforma sottostante diventa interessante. Che è esattamente cosa fornisce orchestrators e utilità di pianificazione. Diamo un'occhiata breve qui:

-   **Utilità di pianificazione * * * *"Pianificazione" si intende la possibilità per un amministratore caricare un file del servizio in un sistema host che consente di stabilire come eseguire un contenitore specifico. Avvio dei contenitori in un cluster di Docker tende a essere noto come la pianificazione. Sebbene la pianificazione si riferisce all'atto specifico di caricare la definizione del servizio, nel senso più generale, le utilità di pianificazione sono responsabili dell'associazione nel sistema di inizializzazione dell'host per gestire i servizi in qualsiasi capacità necessita.

Un'utilità di pianificazione di cluster con più obiettivi: utilizzo delle risorse del cluster in modo efficiente, lavora con i vincoli di posizione fornita dall'utente, la programmazione rapidamente alle applicazioni non lasciarli in uno stato in sospeso, con una certa "equità", in grado di gestire gli errori, e essere sempre disponibile.

-   **Orchestrazione * * * *piattaforme estendono le funzionalità di gestione del ciclo di vita a carichi di lavoro complessi e multicontainer distribuite in un cluster di host. Mediante l'astrazione all'infrastruttura host, gli strumenti di orchestrazione offrono agli utenti un modo per trattare l'intero cluster come destinazione una singola distribuzione.

Il processo di orchestrazione comporta gli strumenti e una piattaforma in grado di automatizzare tutti gli aspetti della gestione delle applicazioni dalla posizione iniziale o di distribuzione per ogni contenitore. lo spostamento di contenitori in host diversi a seconda dell'host o per l'integrità delle prestazioni. controllo delle versioni e in sequenza gli aggiornamenti e le funzioni che supportano la scalabilità e failover; monitoraggio dell'integrità e molto altro ancora.

Orchestrazione si intende che fa riferimento al contenitore pianificazione, la gestione di cluster e probabilmente il provisioning di altri host.

Le funzionalità fornite da orchestrators e utilità di pianificazione sono molto complesse da sviluppare e creare da zero e pertanto è in genere preferibile rendere uso di soluzioni di orchestrazione offerti dai fornitori.


>[!div class="step-by-step"]
[Precedente](index.md)
[Successivo](manage-production-docker-environments.md)
