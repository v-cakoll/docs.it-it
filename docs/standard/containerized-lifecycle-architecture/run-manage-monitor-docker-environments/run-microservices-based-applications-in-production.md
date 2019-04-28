---
title: Eseguire applicazioni composte e basate su microservizi in ambienti di produzione
description: Scopri i componenti chiave per eseguire applicazioni basate su contenitori nell'ambiente di produzione
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 52cf273194bff10192b06d236bda7c1cbea1abd8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921589"
---
# <a name="run-composed-and-microservices-based-applications-in-production-environments"></a>Eseguire applicazioni composte e basate su microservizi in ambienti di produzione

Le applicazioni composte da più microservizi devono essere distribuite in cluster dell'agente di orchestrazione per semplificare la complessità della distribuzione e renderlo utilizzabile dal punto di vista dell'IT. Senza un cluster dell'agente di orchestrazione, sarebbe difficile da distribuire e scalare orizzontalmente un'applicazione di microservizi complessi.

## <a name="introduction-to-orchestrators-schedulers-and-container-clusters"></a>Introduzione per gli agenti di orchestrazione, le utilità di pianificazione e i cluster del contenitore

In precedenza in questo e-book *cluster* e *le utilità di pianificazione* sono stati introdotti come parte della discussione sull'architettura software e sviluppo. Kubernetes e Service Fabric sono esempi di cluster Docker. Entrambi questi agenti di orchestrazione può eseguire come parte dell'infrastruttura fornito da Microsoft Azure Kubernetes Service.

Quando le applicazioni sono con scalabilità orizzontale tra più sistemi host, la possibilità di gestire ogni sistema host e sottraggono la complessità della piattaforma sottostante diventa interessante. Questo è esattamente ciò che forniscono gli agenti di orchestrazione e utilità di pianificazione. Diamo un rapido sguardo qui:

- **Utilità di pianificazione**. "Pianificazione" si riferisce alla possibilità che un amministratore caricare un file del servizio in un sistema host che consente di stabilire come eseguire un contenitore specifico. L'avvio dei contenitori in un cluster Docker tende a essere noto come programmazione. Anche se la pianificazione si riferisce all'atto specifico di caricare la definizione del servizio, nel senso più generale, le utilità di pianificazione sono responsabile dell'uso di hook nel sistema di inizializzazione dell'host per gestire i servizi in qualsiasi capacità necessaria.

   Un'utilità di pianificazione di cluster ha più obiettivi: utilizzo delle risorse del cluster in modo efficiente, lavora con i vincoli di posizionamento fornito dall'utente, la programmazione di applicazioni rapidamente di lasciarli non in sospeso, con un grado di "equità", in grado di gestire gli errori, e essere sempre disponibile.

- **Gli agenti di orchestrazione**. Piattaforme di estendono le funzionalità di gestione del ciclo di vita per i carichi di lavoro complessi e multi-contenitore distribuiti in un cluster di host. Tramite l'astrazione dell'infrastruttura di host, gli strumenti di orchestrazione concedere agli utenti un modo per trattare tutto il cluster come destinazione di distribuzione singolo.

   Il processo di orchestrazione implica strumenti e una piattaforma che consente di automatizzare tutti gli aspetti della gestione delle applicazioni dalla posizione iniziale o la distribuzione per ogni contenitore. spostando i contenitori in host diversi a seconda del relativo host o per l'integrità delle prestazioni. controllo delle versioni e in sequenza gli aggiornamenti e le funzioni che supportano la scalabilità e il failover, monitoraggio dell'integrità e molto altro ancora.

   Orchestrazione è un termine generico che fa riferimento al contenitore di pianificazione, gestione del cluster e possibilmente il provisioning di altri host.

Le funzionalità offerte da agenti di orchestrazione e utilità di pianificazione sono complesse da sviluppare e creare da zero, pertanto in genere si usano soluzioni di orchestrazione offerte dai fornitori.

>[!div class="step-by-step"]
>[Precedente](index.md)
>[Successivo](manage-production-docker-environments.md)
