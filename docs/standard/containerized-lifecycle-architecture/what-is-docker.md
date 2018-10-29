---
title: Che cos'è Docker?
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.openlocfilehash: 056fb613c078cc407380060dc11890406ac8cffd
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2018
ms.locfileid: "50197678"
---
# <a name="what-is-docker"></a>Che cos'è Docker?

[Docker](https://www.docker.com/) è un [progetto open source](https://github.com/docker/docker) per automatizzare la distribuzione di applicazioni come contenitori portabili e autosufficienti eseguibili nel cloud o in locale (vedere la figura 1 - 2). Docker è anche un [aziendale](https://www.docker.com/) che Alza di livello e sviluppa questo tecnologico, lavorando in collaborazione con il cloud, Linux e i fornitori di Windows, inclusa Microsoft.

![](./media/image2.png)

Figura 1-2: Docker distribuisce contenitori a tutti i livelli del cloud ibrido

I contenitori di immagini Docker possono essere eseguiti in modo nativo in Linux e Windows. Tuttavia, le immagini di Windows possono eseguire solo negli host di Windows e possono eseguire immagini Linux solo negli host di Linux, vale a dire un server host o una macchina virtuale.

Gli sviluppatori possono usare gli ambienti di sviluppo in Windows, Linux o macOS. Nel computer di sviluppo, lo sviluppatore esegue un host Docker a Docker quale vengono distribuite le immagini, tra cui l'app e le relative dipendenze. Gli sviluppatori che lavorano in Linux o Mac usano un host Docker basato su Linux e possono creare immagini solo per i contenitori Linux. (Sviluppatori che lavorano nel Mac è possono modificare il codice o eseguire l'interfaccia della riga di comando di Docker \[CLI\] da macOS, ma, a partire dalla stesura di questo articolo, i contenitori non vengono eseguiti direttamente in macOS.) Gli sviluppatori che lavorano in Windows possono creare le immagini sia per i contenitori Linux che per i contenitori Windows.

Per ospitare i contenitori negli ambienti di sviluppo e offrire strumenti di sviluppo aggiuntivi, Docker fornisce [Docker Community Edition (CE)](https://www.docker.com/community-edition) per Windows o per macOS. Questi i prodotti installano la macchina virtuale necessaria (host Docker) per l'hosting dei contenitori. Docker mette anche a disposizione [Docker Enterprise Edition (EE)](https://www.docker.com/enterprise-edition), progettato per lo sviluppo aziendale e usato dai team IT che compilano, distribuiscono ed eseguono applicazioni critiche di grandi dimensioni nell'ambiente di produzione.

Per eseguire i [contenitori Windows](/virtualization/windowscontainers/about/), esistono due tipi di runtime:

-   **Contenitore di Windows Server** questo runtime fornisce isolamento dell'applicazione tramite la tecnologia di isolamento dei processi e dello spazio dei nomi. Un contenitore Windows Server condivide un kernel con l'host del contenitore e con tutti i contenitori in esecuzione nell'host.

-   **Contenitore di Hyper-V** si amplia l'isolamento fornito dai contenitori di Windows Server eseguendo ciascun contenitore in una macchina virtuale altamente ottimizzata. In questa configurazione, il kernel dell'host dei contenitori non è condiviso con i contenitori Hyper-V per fornire un isolamento migliore.

Le immagini per questi contenitori vengono create nello stesso modo e funzionano allo stesso. La differenza consiste nella modalità di creazione del contenitore dall'immagine, ovvero l'esecuzione di un contenitore di Hyper-V richiede un parametro aggiuntivo. Per informazioni dettagliate, vedere [Contenitori Hyper-V](/virtualization/windowscontainers/about/).

## <a name="comparing-docker-containers-with-vms"></a>Confronto tra contenitori Docker con macchine virtuali

La figura 1-3 illustra un confronto tra le macchine virtuali e Docker dei contenitori.

Poiché i contenitori richiedono molte meno risorse (ad esempio, non è necessario un sistema operativo completo), sono facili da distribuire e si avviano rapidamente. Questo rende possibile avere un aumento della densità, vale a dire che è possibile eseguire più servizi nella stessa unità hardware, riducendo i costi.

Come effetto collaterale dell'esecuzione sullo stesso kernel, per ottenere un isolamento minore rispetto alle macchine virtuali.

L'obiettivo principale di un'immagine è rendere l'ambiente (dipendenze) uguale su distribuzioni diverse. Questo significa che è possibile eseguirne il debug nel computer corrente e quindi distribuirla in un altro computer con lo stesso ambiente garantito.

Un'immagine del contenitore è un modo per creare pacchetti di un'app o un servizio e distribuirlo in modo affidabile e riproducibile. In questo senso, Docker non è solo una tecnologia, è anche una filosofia e un processo.

Quando si usa Docker, gli sviluppatori non ascolterai ad esempio, "Funziona sul mio computer, perché non nell'ambiente di produzione?" È possibile semplicemente specificare "È in esecuzione in Docker," perché l'applicazione Docker in pacchetto può essere eseguita in qualsiasi ambiente Docker supportato e verrà eseguito il modo in cui che si intendeva su tutte le destinazioni di distribuzione (sviluppo, controllo qualità, staging, produzione e così via.).

![](./media/image3.png)

Figura 1-3: confronto tra le macchine virtuali tradizionali per i contenitori Docker


>[!div class="step-by-step"]
[Precedente](index.md)
[Successivo](docker-terminology.md)
