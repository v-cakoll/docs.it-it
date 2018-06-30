---
title: Che cos'è Docker?
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.openlocfilehash: 2dfff13f00d4ea0e57161c21d7773eead41c28ee
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105385"
---
# <a name="what-is-docker"></a>Che cos'è Docker?

[Docker](https://www.docker.com/) è un [progetto open source](https://github.com/docker/docker) per automatizzare la distribuzione di applicazioni come contenitori portabile, autosufficiente eseguibili nel cloud o locale (vedere Figura 1 - 2). Docker è anche un [aziendale](https://www.docker.com/) che Alza di livello e vengono successivamente sviluppati questa tecnologia, lavorare in collaborazione con fornitori di Windows, inclusi Microsoft di cloud, Linux e.

![](./media/image2.png)

Figura 1-2: Docker consente di distribuire i contenitori in tutti i livelli di cloud ibrido

Contenitori di docker immagine eseguibili in modo nativo Linux e Windows. Tuttavia, le immagini di Windows possono eseguire solo negli host Windows e le immagini Linux può essere eseguito solo gli host Linux, vale a dire un server host o una macchina virtuale.

Gli sviluppatori possono utilizzare gli ambienti di sviluppo per Windows, Linux o macOS. Nel computer di sviluppo, lo sviluppatore viene eseguito un host Docker in cui Docker vengono distribuite le immagini, tra cui l'app e le relative dipendenze. Gli sviluppatori che lavorano in Linux o nel Mac, usare un host Docker basati su Linux, e possono creare immagini solo per i contenitori di Linux. (Agli sviluppatori che lavorano nel Mac, è possono modificare il codice o eseguire l'interfaccia della riga di comando di Docker \[CLI\] da macOS, ma in questo modo, i contenitori non eseguito direttamente sulle macOS.) Gli sviluppatori che lavorano su Windows possono creare immagini per Linux o i contenitori di Windows.

Per ospitare i contenitori in ambienti di sviluppo e fornisce gli strumenti di sviluppo aggiuntive, viene fornito Docker [Docker Community Edition (CE)](https://www.docker.com/community-edition) per Windows o per macOS. Questi prodotti installano la macchina virtuale necessaria (host Docker) per ospitare i contenitori. Docker rese disponibili anche [Docker Enterprise Edition (EE)](https://www.docker.com/enterprise-edition), che è progettato per lo sviluppo enterprise e viene usato dai team IT impegnati nella compilazione, spedire ed eseguire applicazioni business-critical di grandi dimensioni nell'ambiente di produzione.

Per eseguire [i contenitori di Windows](https://msdn.microsoft.com/virtualization/windowscontainers/about/about_overview), esistono due tipi di runtime:

-   **Contenitore di Windows Server** questo runtime fornisce isolamento dell'applicazione tramite la tecnologia di isolamento dei processi e dello spazio dei nomi. Un contenitore Windows Server condivide un kernel con l'host del contenitore e con tutti i contenitori in esecuzione nell'host.

-   **Contenitore di Hyper-V** verrà espanso l'isolamento fornito dai contenitori di Windows Server eseguendo ciascun contenitore in una macchina virtuale altamente ottimizzata. In questa configurazione, il kernel dell'host dei contenitori non è condiviso con i contenitori Hyper-V per fornire un isolamento migliore.

Le immagini per questi contenitori vengono create nello stesso modo e funzionano allo stesso. La differenza consiste nel modo in cui la creazione del contenitore dall'immagine, ovvero l'esecuzione di un contenitore di Hyper-V richiede un parametro aggiuntivo. Per informazioni dettagliate, vedere [Contenitori Hyper-V](https://msdn.microsoft.com/virtualization/windowscontainers/about/about_overview).

## <a name="comparing-docker-containers-with-vms"></a>Confronto tra contenitori di Docker con le macchine virtuali

Figura 1-3 viene illustrato un confronto tra le macchine virtuali e Docker dei contenitori.

Poiché i contenitori richiedono molto meno risorse (ad esempio, non richiedono un sistema operativo completo), sono facili da distribuire e avvio veloce. Questo rende possibile avere maggiore densità, vale a dire che è possibile eseguire più servizi nella stessa unità di hardware, riducendo i costi.

Come effetto collaterale dell'esecuzione sullo stesso kernel, meno isolamento rispetto a macchine virtuali.

L'obiettivo principale di un'immagine è rendere l'ambiente (dipendenze) uguale su distribuzioni diverse. Questo significa che è possibile eseguirne il debug nel computer corrente e quindi distribuirla in un altro computer con lo stesso ambiente garantito.

Un'immagine contenitore è un modo per creare un pacchetto un'app o un servizio e distribuirlo in modo affidabile e riproducibile. In questo senso, Docker non è solo una tecnologia, è anche una filosofia e un processo.

Quando si usa Docker, è Impossibile ascoltare gli sviluppatori ad esempio, "Funziona nel computer, non vengono visualizzati nell'ambiente di produzione?" È sufficiente dire, "Viene eseguito in Docker," perché il pacchetto dell'applicazione Docker può essere eseguito in qualsiasi ambiente Docker supportato e verrà eseguito il modo in cui che si intendeva su tutte le destinazioni di distribuzione (sviluppo, QA, gestione temporanea, produzione e così via.).

![](./media/image3.png)

Figura 1-3: confronto delle tradizionali macchine virtuali per i contenitori di Docker


>[!div class="step-by-step"]
[Precedente](index.md)
[Successivo](docker-terminology.md)
