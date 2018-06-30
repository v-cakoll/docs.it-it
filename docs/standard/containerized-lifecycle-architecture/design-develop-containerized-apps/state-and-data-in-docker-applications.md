---
title: Stato e dati nelle applicazioni di Docker
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 438733b2cde1d4eff178a5fd4a4ed0bb93804f76
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105449"
---
# <a name="state-and-data-in-docker-applications"></a>Stato e dati nelle applicazioni di Docker

Una primitiva di contenitori è immutabilità. Se confrontata a una macchina virtuale, i contenitori non scompaiano come un problema comune. Una macchina virtuale potrebbe non riuscire in varie forme da processi di messaggi non recapitabili, overload della CPU o un disco con registrazione completo o non riuscito. Ancora, è probabile che la macchina virtuale sia disponibile e le unità RAID sono comuni per assicurare che gli errori di unità mantengono i dati.

Tuttavia, i contenitori sono considerati per essere istanze dei processi. Un processo non mantiene lo stato durevole. Anche se un contenitore è possibile scrivere nello spazio di archiviazione locale, il presupponendo che tale istanza saranno intorno all'infinito sarebbe equivalente al presupponendo che una singola copia della memoria sarà durevole. Si deve presupporre che i contenitori, ad esempio i processi, vengono duplicati, terminato, o, quando gestito con un agente di orchestrazione di contenitore, potrebbero essere spostati.

Docker utilizza una funzionalità nota come un *sovrapposizione system file* per implementare un processo copy-on-write che archivia le informazioni aggiornate nel file System radice di un contenitore, rispetto all'immagine originale in cui è basato. Queste modifiche vengono perse se il contenitore viene successivamente eliminato dal sistema. Un contenitore, pertanto, non dispone di archiviazione permanente per impostazione predefinita. Sebbene sia possibile salvare lo stato di un contenitore, progettazione di un sistema di risoluzione di questo problema sarebbe in conflitto con il principio di architettura a contenitori.

Per gestire i dati persistenti in applicazioni di Docker, sono disponibili soluzioni comuni:

-   [**I volumi di dati**](https://docs.docker.com/engine/tutorials/dockervolumes/) questi montare all'host, come indicato semplicemente.

-   [**I contenitori dei volumi di dati**](https://docs.docker.com/engine/tutorials/dockervolumes/#/creating-and-mounting-a-data-volume-container) forniscono spazio di archiviazione condiviso tra contenitori, utilizzando un contenitore esterno che può scorrere.

-   [**I plug-in volume**](https://docs.docker.com/engine/tutorials/dockervolumes/#/mount-a-shared-storage-volume-as-a-data-volume) questi montare i volumi a sedi remote, che fornisce la persistenza a lungo termine.

-   **Origini dati remote** gli esempi includono database SQL e NO-SQL o memorizzare nella cache servizi come Redis.

-   [**Archiviazione di Azure**](https://docs.microsoft.com/azure/storage/) fornisce geografica distribuibile piattaforma come archiviazione di servizio (PaaS), che offre il meglio dei contenitori di persistenza come a lungo termine.

I volumi di dati in modo speciale designati directory all'interno di uno o più contenitori che consentono di ignorare il [unione File System](https://docs.docker.com/v1.8/reference/glossary#union-file-system). I volumi di dati sono progettati per gestire i dati, indipendentemente dal ciclo di vita del contenitore. Docker pertanto mai eliminati automaticamente i volumi quando si rimuove un contenitore, né lo saranno è volumi "garbage raccogliere" privi di riferimenti da un contenitore. Il sistema operativo host possono esplorare e modificare i dati in qualsiasi volume liberamente, che è semplicemente un altro motivo per utilizzare i volumi di dati con cautela.

Un [contenitore di volumi di dati](https://docs.docker.com/v1.8/userguide/dockervolumes/) rappresenta una miglioria volumi di dati regolare. È sostanzialmente un contenitore inattivo dotato di uno o più volumi di dati creati in esso contenuti (come descritto in precedenza). Il contenitore del volume di dati fornisce l'accesso ai contenitori da un punto di montaggio centrale. Il vantaggio di questo metodo di accesso è che il percorso dei dati originali, rendendo il contenitore di dati di un punto di montaggio logico. Consente anche di contenitori di "application" accedono i volumi di contenitore di dati devono essere creati e distrutti, mantenendo i dati permanenti in un contenitore dedicato.

Figura 4-5 viene mostrato che regolari volumi Docker possono essere inseriti su archiviazione fuori i contenitori stessi ma entro i limiti fisici server/macchina virtuale host. *I volumi di docker non hanno la possibilità di usare un volume da un host server/macchina virtuale a un altro*.

![](./media/image5.png)

Figura 4-5: volumi di dati e origini dati esterne per i contenitori. app/contenitori

A causa dell'impossibilità di gestire i dati condivisi tra contenitori che vengono eseguiti in host fisici separati, è consigliabile non utilizzare i volumi per i dati aziendali, a meno che l'host Docker è una host predefinita/VM, perché quando si usa Docker containers nell'agente di orchestrazione, i contenitori devono essere spostato da uno a un altro host, a seconda delle ottimizzazioni da eseguire dal cluster.

Pertanto, i volumi di dati regolari sono un meccanismo appropriato per funzionare con i file di traccia, file temporali o qualsiasi concetto simile che non interessano la coerenza dei dati di business se o quando i contenitori vengono spostati tra più host.

Plug-in di volume come [Flocker](https://clusterhq.com/flocker/) forniscono dati in tutti gli host in un cluster. Anche se non tutti i plug-in di volume vengono creati in modo uniforme, volume plug-in genere forniscono esternalizzati nell'archivio permanente affidabile dai contenitori non modificabili.

Origini dati remote e le cache come Database SQL, DocumentDB o una cache remota come Redis rimarrebbe lo stesso come lo sviluppo senza contenitori. Questo è uno dei modi Preferiti e si basa sulla collaudata, per archiviare i dati di business dell'applicazione.


>[!div class="step-by-step"]
[Precedente](monolithic-applications.md)
[Successivo](soa-applications.md)
