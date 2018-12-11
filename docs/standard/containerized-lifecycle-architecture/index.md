---
title: Introduzione ai contenitori e a Docker
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: c2a6b9802bbb995939d33c5c40ef9c1afa1620e5
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148821"
---
# <a name="introduction-to-containers-and-docker"></a>Introduzione ai contenitori e a Docker

La containerizzazione è un approccio allo sviluppo del software in cui un'applicazione o un servizio, le relative dipendenze e la corrispondente configurazione (astratti come file manifesto della distribuzione) sono inclusi in uno stesso pacchetto sotto forma di immagine del contenitore. È quindi possibile testare l'applicazione nel contenitore come unità e distribuirla come istanza dell'immagine del contenitore al sistema operativo host.

Proprio come nel settore delle spedizioni vengono usati container standard per il trasporto delle merci via nave, treno o camion indipendentemente dal contenuto del carico, i contenitori software fungono da unità standard di software in grado di contenere codice e dipendenze diversi. Inserendo il software nei contenitori si consente agli sviluppatori e ai professionisti IT di distribuire tali contenitori in ambienti diversi senza nessuna modifica o con modifiche minime.

I contenitori isolano anche le applicazioni una dall'altra in un sistema operativo condiviso. Le applicazioni in contenitori vengono eseguite in un host contenitore che a sua volta viene eseguito nel sistema operativo (Linux o Windows). I contenitori hanno quindi un footprint notevolmente più ridotto rispetto alle immagini di macchine virtuali.

Ogni contenitore può eseguire un intero servizio o applicazione Web, come illustrato nella figura 1-1.

![](./media/image1.png)

Figura 1-1: Più contenitori in esecuzione in un host contenitore

In questo esempio l'host Docker è un host contenitore e App 1, App 2, Svc 1 e Svc 2 sono applicazioni o servizi in contenitori.

Un altro vantaggio offerto dai contenitori è la scalabilità. È possibile ottenere rapidamente scalabilità orizzontale creando nuovi contenitori per le attività a breve termine. Dal punto di vista di un'applicazione, la *creazione di un'istanza di un'immagine* (creazione di un contenitore) è analoga alla creazione di un'istanza di un processo, come un servizio o un'app Web. Per garantire l'affidabilità, tuttavia, quando si eseguono più istanze della stessa immagine tra più server host, in genere consigliabile ogni contenitore (istanza dell'immagine) per l'esecuzione in un server host diverso o una macchina virtuale in diversi domini di errore.

In breve, i contenitori offrono vantaggi in termini di isolamento, portabilità, flessibilità, scalabilità e controllo nel flusso di lavoro dell'intero ciclo di vita dell'applicazione. Il vantaggio più importante è l'isolamento fornito tra sviluppo e operazioni.

>[!div class="step-by-step"]
>[avanti](what-is-docker.md)