---
title: Introduzione a contenitori e Docker
description: Architettura di microservizi .NET per le applicazioni .NET incluse in contenitori | Introduzione a contenitori e Docker
ms.date: 08/31/2018
ms.openlocfilehash: 364cbc0ba8149be1873df628a1ca243f420e7d0b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73740056"
---
# <a name="introduction-to-containers-and-docker"></a>Introduzione a contenitori e Docker

La containerizzazione è un approccio allo sviluppo del software in cui un'applicazione o un servizio, le relative dipendenze e la corrispondente configurazione (astratti come file manifesto della distribuzione) sono inclusi in uno stesso pacchetto sotto forma di immagine del contenitore. L'applicazione inclusa nel contenitore può essere testata come unità e distribuita come istanza dell'immagine del contenitore al sistema operativo host.

Proprio come i container consentono il trasporto delle merci via nave, treno o camion indipendentemente dal contenuto del carico, i contenitori software fungono da unità standard di distribuzione software in grado di contenere codice e dipendenze diversi. Questa modalità di containerizzazione del software consente a sviluppatori e professionisti IT di distribuire applicazioni tra ambienti diversi con modifiche minime se non inesistenti.

I contenitori contribuiscono inoltre a isolare le applicazioni una dall'altra in un sistema operativo condiviso. Le applicazioni incluse in contenitori sono eseguite in un host contenitore che a sua volta viene eseguito nel sistema operativo (Linux o Windows). I contenitori hanno pertanto un footprint notevolmente più ridotto rispetto alle immagini di macchine virtuali.

Ogni contenitore può eseguire un intero servizio e applicazione Web, come illustrato nella figura 2-1. In questo esempio l'host Docker è un host contenitore e App1, App2, Svc 1 e Svc 2 sono applicazioni o servizi inclusi nei contenitori.

![Diagramma che mostra quattro contenitori in esecuzione in una macchina virtuale o in un server.](./media/index/multiple-containers-single-host.png)

**Figura 2-1**. Più contenitori in esecuzione in un host contenitore

Un altro vantaggio della containerizzazione consiste nella scalabilità. La scalabilità orizzontale viene rapidamente garantita con la creazione di nuovi contenitori per le attività a breve termine. Dal punto di vista dell'applicazione, la creazione di un'istanza di un'immagine (corrispondente alla creazione di un contenitore) è analoga alla creazione di un'istanza di un processo, come un servizio o un'app Web. Per l'affidabilità, tuttavia, quando si eseguono più istanze della stessa immagine tra più server host, in genere si fa in modo che ogni contenitore (istanza dell'immagine) sia eseguito in un server host o in una macchina virtuale diversa in domini di errore differenti.

In breve, i contenitori assicurano vantaggi in termini di isolamento, portabilità, flessibilità, scalabilità e controllo nel flusso di lavoro dell'intero ciclo di vita dell'applicazione. Il vantaggio più importante è l'isolamento dell'ambiente fornito tra sviluppo e operazioni.

>[!div class="step-by-step"]
>[Successivo](../index.md)
>[precedente](docker-defined.md)
