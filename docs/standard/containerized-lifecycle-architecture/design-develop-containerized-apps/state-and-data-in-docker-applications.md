---
title: Stato e dati nelle applicazioni di Docker
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: a9f0750dbcffd051e9dae7d9f4f74b921e30af29
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="state-and-data-in-docker-applications"></a>Stato e dati nelle applicazioni di Docker

Una primitiva di contenitori è immutabilità. Rispetto a una macchina virtuale, i contenitori non interrompersi quando un problema comune. Una macchina virtuale potrebbe non riuscire in varie forme da processi di messaggi non recapitabili, overload della CPU o un disco pieno o non riuscito. Ancora, è probabile che la macchina virtuale sia disponibile e unità RAID sono comuni per assicurare che gli errori di unità mantengono i dati.

Tuttavia, i contenitori sono considerati per essere istanze dei processi. Un processo non mantiene lo stato durevole. Anche se un contenitore è possibile scrivere nello spazio di archiviazione locale, presupponendo che tale istanza saranno intorno all'infinito sarebbe essere equivalente al presupponendo che una singola copia della memoria sarà durevole. Si deve presupporre che i contenitori, ad esempio i processi, vengono duplicati, terminato, o quando gestito con un agente di orchestrazione del contenitore, potrebbero essere spostati.

Docker utilizza una funzionalità nota come un *sovrapposizione sistema file* per implementare un processo copy-on-write che archivia le informazioni aggiornate nel file System di radice di un contenitore, rispetto all'immagine originale su cui è basato. Tali modifiche vengono perse se il contenitore viene successivamente eliminato dal sistema. Un contenitore, pertanto, non dispone di archivio permanente per impostazione predefinita. Sebbene sia possibile salvare lo stato di un contenitore, progettazione di un sistema di risoluzione di questo problema sarebbe in conflitto con il principio dell'architettura di contenitore.

Per gestire i dati nelle applicazioni di Docker, sono disponibili soluzioni comuni:

-   [**I volumi di dati**](https://docs.docker.com/engine/tutorials/dockervolumes/) questi montare all'host, come indicato semplicemente.

-   [**Contenitori di volumi di dati**](https://docs.docker.com/engine/tutorials/dockervolumes/#/creating-and-mounting-a-data-volume-container) forniscono spazio di archiviazione condiviso tra contenitori, utilizzando un contenitore esterno che è possibile scorrere.

-   [**I plug-in di volume**](https://docs.docker.com/engine/tutorials/dockervolumes/#/mount-a-shared-storage-volume-as-a-data-volume) questi montare i volumi a sedi remote, che fornisce la persistenza a lungo termine.

-   **Origini dati remote** gli esempi includono database NO SQL e SQL Server o servizi come Redis cache.

-   [**Archiviazione di Azure**](https://docs.microsoft.com/azure/storage/) fornisce geografica distribuibile piattaforma come archiviazione di servizio (PaaS), offre il meglio dei contenitori di persistenza come a lungo termine.

I volumi di dati appositamente progettati directory all'interno di uno o più contenitori che consentono di ignorare il [unione di File System](https://docs.docker.com/v1.8/reference/glossary#union-file-system). I volumi di dati sono progettati per gestire i dati, indipendentemente dal ciclo di vita del contenitore. Docker pertanto mai Elimina automaticamente i volumi quando si rimuovere un contenitore, né verranno volumi "garbage raccogliere" che non fa riferimento non è più un contenitore. Il sistema operativo host può esplorare e modificare i dati in qualsiasi volume liberamente, che è semplicemente un altro motivo per utilizzare i volumi di dati con cautela.

Oggetto [contenitore del volume di dati](https://docs.docker.com/v1.8/userguide/dockervolumes/) rappresenta un miglioramento rispetto ai volumi di dati normali. È sostanzialmente un contenitore inattivo che ha creati all'interno di esso, come descritto in precedenza, uno o più volumi di dati. Il contenitore del volume di dati fornisce l'accesso ai contenitori da un punto di montaggio centrale. Il vantaggio di questo metodo di accesso è che il percorso dei dati originali, rendendo il contenitore di dati di un punto di montaggio logico. Consente inoltre l'accesso a volumi di contenitore di dati devono essere creati e distrutti mantenendo i dati permanenti in un contenitore dedicato contenitori di "application".

Figura 4-5 mostra che regolari volumi Docker possono essere inseriti su archiviazione out-of contenitori stessi ma entro i limiti di host macchina virtuale server/fisica. *Volumi di docker non hanno la possibilità di utilizzare un volume da un host server/macchina virtuale a un altro*.

![](./media/image5.png)

Figura 4-5: volumi di dati e origini dati esterne per i contenitori. app/contenitori

A causa dell'impossibilità di gestire i dati condivisi tra contenitori che vengono eseguiti in host fisici separati, è consigliabile non utilizzare volumi per i dati aziendali, a meno che l'host Docker è una host predefinita/VM, perché quando si utilizzano i contenitori di Docker in un agente di orchestrazione, contenitori devono essere spostati da uno a un altro host, a seconda delle ottimizzazioni da eseguire dal cluster.

Pertanto, i volumi di dati regolari sono un meccanismo efficace per lavorare con file di traccia, il file temporale o qualsiasi concetto simile che non interessano la coerenza dei dati aziendali se o quando i contenitori vengono spostati tra più host.

Plug-in di volume come [Flocker](https://clusterhq.com/flocker/) forniscono dati in tutti gli host in un cluster. Anche se non tutti i plug-in di volume vengono creati in modo uniforme, volume plug-in genere forniscono esternalizzati archiviazione affidabile permanente dai contenitori non modificabili.

Origini dati remote e memorizza nella cache come Database SQL, DocumentDB o una cache remota come Redis rimarrebbe lo stesso come lo sviluppo senza contenitori. Questo è uno dei modi Preferiti e comprovati, per archiviare i dati delle applicazioni aziendali.


>[!div class="step-by-step"]
[Precedente] (monolitico applications.md) [Avanti] (applications.md soa)
