---
title: Introduzione a contenitori e Docker
description: Ottenere una panoramica generale dei vantaggi principali derivanti dall'uso di Docker.
ms.date: 02/15/2019
ms.openlocfilehash: a03c67ed4fbc55c84e69fba5b7978863c8305e00
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "70295672"
---
# <a name="introduction-to-containers-and-docker"></a>Introduzione ai contenitori e a Docker

*La containerizzazione è un approccio allo sviluppo del software in cui un'applicazione o un servizio, le relative dipendenze e la corrispondente configurazione (astratti come file manifesto della distribuzione) sono inclusi in uno stesso pacchetto sotto forma di immagine del contenitore. È quindi possibile testare l'applicazione nel contenitore come unità e distribuirla come istanza dell'immagine del contenitore al sistema operativo host.*

Proprio come i container consentono il trasporto delle merci via nave, treno o camion indipendentemente dal contenuto del carico, i contenitori software fungono da unità standard di distribuzione software in grado di contenere codice e dipendenze diversi. Questa modalità di containerizzazione del software consente a sviluppatori e professionisti IT di distribuire applicazioni tra ambienti diversi con modifiche minime se non inesistenti.

I contenitori contribuiscono inoltre a isolare le applicazioni una dall'altra in un sistema operativo condiviso. Le applicazioni incluse in contenitori sono eseguite in un host contenitore che a sua volta viene eseguito nel sistema operativo (Linux o Windows). I contenitori hanno pertanto un footprint notevolmente più ridotto rispetto alle immagini di macchine virtuali.

Ogni contenitore può eseguire un intero servizio o applicazione Web, come illustrato nella figura 1-1. In questo esempio l'host Docker è un host contenitore e App1, App2, Svc1 e Svc2 sono servizi o applicazioni inclusi nei contenitori.

![Due applicazioni e due servizi in esecuzione nel sistema operativo in una macchina virtuale o un server fisico](./media/image1.png)

**Figura 1-1**. Più contenitori in esecuzione in un host contenitore

Un altro vantaggio offerto dai contenitori è la scalabilità. La scalabilità orizzontale viene rapidamente garantita con la creazione di nuovi contenitori per le attività a breve termine. Dal punto di vista dell'applicazione, la creazione di un'istanza di un'immagine (corrispondente alla creazione di un contenitore) è analoga alla creazione di un'istanza di un processo, come un servizio o un'app Web. Per l'affidabilità, tuttavia, quando si eseguono più istanze della stessa immagine tra più server host, in genere si fa in modo che ogni contenitore (istanza dell'immagine) sia eseguito in un server host o in una macchina virtuale diversa in domini di errore differenti.

In breve, i contenitori offrono vantaggi in termini di isolamento, portabilità, flessibilità, scalabilità e controllo nel flusso di lavoro dell'intero ciclo di vita dell'applicazione. Il vantaggio più importante è l'isolamento dell'ambiente fornito tra sviluppo e operazioni.

>[!div class="step-by-step"]
>[avanti](what-is-docker.md)
