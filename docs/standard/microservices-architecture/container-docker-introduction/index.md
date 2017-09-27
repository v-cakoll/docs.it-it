---
title: Introduzione a contenitori e Docker
description: Architettura di microservizi .NET per le applicazioni .NET incluse in contenitori | Introduzione a contenitori e Docker
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.translationtype: HT
ms.sourcegitcommit: 9bb64ea7199f5699ff166d1affb7f8126dcc6612
ms.openlocfilehash: 28a6e17f9c36d937ef323276c7ccc8c099844be7
ms.contentlocale: it-it
ms.lasthandoff: 09/05/2017

---
# <a name="introduction-to-containers-and-docker"></a>Introduzione a contenitori e Docker

La containerizzazione è un approccio allo sviluppo del software in cui un'applicazione o un servizio, le relative dipendenze e la corrispondente configurazione (astratti come file manifesto della distribuzione) sono inclusi in uno stesso pacchetto sotto forma di immagine del contenitore. L'applicazione inclusa nel contenitore può essere testata come unità e distribuita come istanza dell'immagine del contenitore al sistema operativo host.

Proprio come i container consentono il trasporto delle merci via nave, treno o camion indipendentemente dal contenuto del carico, i contenitori software fungono da unità standard di software in grado di contenere codice e dipendenze diversi. Questa modalità di containerizzazione del software consente a sviluppatori e professionisti IT di distribuire applicazioni tra ambienti diversi con modifiche minime se non inesistenti.

I contenitori contribuiscono inoltre a isolare le applicazioni una dall'altra in un sistema operativo condiviso. Le applicazioni incluse in contenitori sono eseguite in un host contenitore che a sua volta viene eseguito nel sistema operativo (Linux o Windows). I contenitori hanno pertanto un footprint notevolmente più ridotto rispetto alle immagini di macchine virtuali.

Ogni contenitore può eseguire un intero servizio e applicazione Web, come illustrato nella figura 2-1. In questo esempio l'host Docker è un host contenitore e App1, App2, Svc 1 e Svc 2 sono applicazioni o servizi inclusi nei contenitori.

![](./media/image1.png)

**Figura 2-1**. Più contenitori in esecuzione in un host contenitore

Un altro vantaggio della containerizzazione consiste nella scalabilità. La scalabilità orizzontale viene rapidamente garantita con la creazione di nuovi contenitori per le attività a breve termine. Dal punto di vista dell'applicazione, la creazione di un'istanza di un'immagine (corrispondente alla creazione di un contenitore) è analoga alla creazione di un'istanza di un processo, come un servizio o un'app Web. Per l'affidabilità, tuttavia, quando si eseguono più istanze della stessa immagine tra più server host, in genere si fa in modo che ogni contenitore (istanza dell'immagine) sia eseguito in un server host o in una macchina virtuale diversa in domini di errore differenti.

In breve, i contenitori assicurano vantaggi in termini di isolamento, portabilità, flessibilità, scalabilità e controllo nel flusso di lavoro dell'intero ciclo di vita dell'applicazione. Il vantaggio più importante è l'isolamento fornito tra sviluppo e operazioni.


>[!div class="step-by-step"]
[Precedente] (../index.md) [Successivo] (docker-defined.md)

