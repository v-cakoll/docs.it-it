---
title: Stato e dati nelle applicazioni di Docker
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 78db191bdec4c25c11728d819d89eaaaff4bd7da
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2018
ms.locfileid: "46532467"
---
# <a name="state-and-data-in-docker-applications"></a>Stato e dati nelle applicazioni di Docker

Una primitiva di contenitori è immutabilità. Rispetto a una macchina virtuale, i contenitori non interrompersi quando una situazione comune. Una macchina virtuale potrebbe non riuscire in varie forme da processi inattivi, overload della CPU o un disco con registrazione completo o non riuscito. Tuttavia, si prevede che la macchina virtuale sia disponibile e unità RAID sono usuali per assicurare che i dati di gestire errori delle unità.

Tuttavia, i contenitori considerati come istanze dei processi. Un processo non mantiene lo stato durevole. Anche se un contenitore può scrivere la risorsa di archiviazione locale, presupponendo che tale istanza saranno intorno a tempo indeterminato corrisponderebbe a presupponendo che una copia singola memoria sia durevole. Si deve presupporre che i contenitori, come i processi, vengono duplicati, abbattuti o, quando gestito con un agente di orchestrazione del contenitore, potrebbero essere spostati.

Docker Usa una funzionalità nota come un *sovrimpressione di file system* per implementare un processo di copia su scrittura che archivia le informazioni aggiornate nel file System radice di un contenitore, rispetto all'immagine originale su cui è basato. Queste modifiche vengono perse se il contenitore viene successivamente eliminato dal sistema. Un contenitore, pertanto, non è un archivio permanente per impostazione predefinita. Sebbene sia possibile salvare lo stato di un contenitore, la progettazione di un sistema di risoluzione di questo problema sarà in conflitto con il principio di architettura a contenitori.

Per gestire i dati persistenti nelle applicazioni di Docker, sono disponibili soluzioni comuni:

-   [**I volumi di dati**](https://docs.docker.com/engine/tutorials/dockervolumes/) questi montati nell'host, quanto appena descritto.

-   [**I contenitori dei volumi di dati**](https://docs.docker.com/engine/tutorials/dockervolumes/#/creating-and-mounting-a-data-volume-container) offrono archiviazione condivisa tra contenitori, usando un contenitore esterno che può scorrere.

-   [**I plug-in di volume**](https://docs.docker.com/engine/tutorials/dockervolumes/#/mount-a-shared-storage-volume-as-a-data-volume) questi montare i volumi a sedi remote, che fornisce la persistenza a lungo termine.

-   **Origini dati remote** esempi includono i database SQL e NO-SQL o servizi di cache come Redis.

-   [**Archiviazione di Azure**](https://docs.microsoft.com/azure/storage/) questa fornisce geografica distribuibile piattaforma come una risorsa di archiviazione del servizio (PaaS), che offre il meglio dei contenitori di persistenza come a lungo termine.

I volumi di dati in modo speciale designati directory all'interno di uno o più contenitori che ignorano il [unione File System](https://docs.docker.com/glossary/?term=Union%20file%20system). I volumi di dati sono progettati per gestire i dati, indipendentemente dal ciclo di vita del contenitore. Docker pertanto mai eliminati automaticamente i volumi quando si rimuovere un contenitore, né verranno "garbage raccogliere" volumi che non fanno riferimento non è più un contenitore. Il sistema operativo host può esplorare e modificare i dati in qualsiasi volume liberamente, che è semplicemente un altro motivo per utilizzare i volumi di dati in modo sporadico.

Oggetto [contenitore di volumi di dati](https://docs.docker.com/glossary/?term=volume) rappresenta una miglioria normali volumi di dati. È sostanzialmente un contenitore inattivo che ha creati all'interno di esso, come descritto in precedenza, uno o più volumi di dati. Il contenitore del volume di dati fornisce l'accesso ai contenitori da un punto di montaggio centrale. Il vantaggio di questo metodo di accesso è che estrae il percorso dei dati originali, rendendo il contenitore di dati di un punto di montaggio logico. Consente inoltre di contenitori "applicazione" l'accesso a volumi di contenitore di dati per essere creati ed eliminati, mantenendo i dati persistenti in un contenitore dedicato.

Figura 4-5 mostra che i volumi Docker normali possono essere inseriti nell'archivio i contenitori stessi ma all'interno dei limiti fisici/macchine Virtuali server host. *I volumi docker non hanno la possibilità di usare un volume da un host server/macchine Virtuali a un altro*.

![](./media/image5.png)

Figura 4-5: i volumi di dati e origini dati esterne per i contenitori. app/contenitori

A causa dell'impossibilità di gestire i dati condivisi tra contenitori che vengono eseguiti in host fisici separati, è consigliabile non usare volumi per i dati aziendali, a meno che l'host Docker è una host predefinita/VM, perché quando si usano i contenitori Docker in un agente di orchestrazione i contenitori devono essere spostati da uno a un altro host, a seconda delle ottimizzazioni da eseguire dal cluster.

Pertanto, i normali volumi di dati sono un meccanismo appropriato per lavorare con i file di traccia, file temporali o qualsiasi concetto simile che non interessano la coerenza dei dati aziendali se o quando i contenitori vengono spostati tra più host.

[Plug-in di volume](https://docs.docker.com/engine/extend/plugins_volume/) forniscono dati in tutti gli host in un cluster. Anche se non tutti i plug-in di volume vengono creati in modo uniforme, plug-in di volume in genere forniscono archiviazione affidabile, persistente esternalizzata dai contenitori non modificabili.

Origini dati remote e le cache, ad esempio Database SQL, DocumentDB o cache remote come Redis sarà quello utilizzato per lo sviluppo senza contenitori. Questo è uno dei modi Preferiti e collaudati per archiviare i dati di business dell'applicazione.


>[!div class="step-by-step"]
[Precedente](monolithic-applications.md)
[Successivo](soa-applications.md)
