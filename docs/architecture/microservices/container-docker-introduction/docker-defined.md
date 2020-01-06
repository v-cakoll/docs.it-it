---
title: Che cos'è Docker?
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Che cos'è Docker?
ms.date: 08/31/2018
ms.openlocfilehash: a53845d3bbcf24f3eaeb98b9e08b6f35a023c30e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337712"
---
# <a name="what-is-docker"></a>Che cos'è Docker?

[Docker](https://www.docker.com/) è un [progetto open source](https://github.com/docker/docker) per automatizzare la distribuzione di app come contenitori portabili e autosufficienti che possono essere eseguiti nel cloud o in locale. Docker è anche una [società](https://www.docker.com/) che promuove e sviluppa questa tecnologia, collaborando con fornitori cloud, Linux e Windows, inclusa Microsoft.

![Diagramma che mostra le posizioni in cui è possibile eseguire i contenitori docker.](./media/docker-defined/docker-containers-run-anywhere.png)

**Figura 2-2**. Docker distribuisce contenitori a tutti i livelli del cloud ibrido.

I contenitori Docker possono essere eseguiti ovunque, in locale nel data center del cliente, in un provider di servizi esterno o nel cloud, in Azure. I contenitori di immagini Docker possono essere eseguiti in modo nativo in Linux e Windows. Tuttavia, le immagini Windows possono essere eseguite solo negli host Windows e le immagini Linux possono essere eseguite in host Linux e in host Windows (con una macchina virtuale Linux Hyper-V, per il momento), dove con host si intende una macchina virtuale o un server.

Gli sviluppatori possono usare gli ambienti di sviluppo in Windows, Linux o macOS. Nel computer di sviluppo lo sviluppatore esegue un host Docker in cui vengono distribuite le immagini Docker, inclusa l'app e le relative dipendenze. Gli sviluppatori che lavorano su Linux o su macOS usano un host Docker basato su Linux e possono creare immagini solo per i contenitori Linux. Gli sviluppatori che lavorano su macOS possono modificare il codice o eseguire l'interfaccia della riga di comando di Docker da macOS, ma al momento della stesura di questo articolo, i contenitori non vengono eseguiti direttamente in macOS. Gli sviluppatori che lavorano su Windows possono creare immagini per i contenitori Linux o Windows.

Per ospitare i contenitori negli ambienti di sviluppo e offrire strumenti di sviluppo aggiuntivi, Docker fornisce [Docker Community Edition (CE)](https://www.docker.com/community-edition) per Windows o per macOS. Questi i prodotti installano la macchina virtuale necessaria (host Docker) per l'hosting dei contenitori. Docker mette anche a disposizione [Docker Enterprise Edition (EE)](https://www.docker.com/enterprise-edition), progettato per lo sviluppo aziendale e usato dai team IT che compilano, distribuiscono ed eseguono applicazioni critiche di grandi dimensioni nell'ambiente di produzione.

Per eseguire i [contenitori Windows](/virtualization/windowscontainers/about/), esistono due tipi di runtime:

- I contenitori Windows Server offrono l'isolamento dell'applicazione tramite una tecnologia di isolamento dei processi e dello spazio dei nomi. Un contenitore Windows Server condivide un kernel con l'host del contenitore e con tutti i contenitori in esecuzione nell'host.

- I contenitori Hyper-V espandono l'isolamento fornito dai contenitori Windows Server tramite l'esecuzione di ogni contenitore in una macchina virtuale con ottimizzazione elevata. In questa configurazione, il kernel dell'host dei contenitori non è condiviso con i contenitori Hyper-V per fornire un isolamento migliore.

Le immagini per questi contenitori vengono create nello stesso modo e funzionano nello stesso modo. La differenza consiste nella modalità di creazione del contenitore dall'immagine. L'esecuzione di un contenitore Hyper-V richiede un parametro aggiuntivo. Per informazioni dettagliate, vedere [Contenitori Hyper-V](https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/hyperv-container).

## <a name="comparing-docker-containers-with-virtual-machines"></a>Confronto tra contenitori Docker e macchine virtuali

La figura 2-3 mostra un confronto tra macchine virtuali e contenitori Docker.

| Macchine virtuali | Contenitori Docker |
| -----------------| ------------------|
|![Diagramma che mostra lo stack hardware/software di una macchina virtuale tradizionale.](./media/docker-defined/virtual-machine-hardware-software.png)|![Diagramma che mostra lo stack hardware/software per i contenitori docker.](./media/docker-defined/docker-container-hardware-software.png)|
|Le macchine virtuali includono l'applicazione, le librerie o i file binari necessari e un sistema operativo guest completo. La virtualizzazione completa richiede più risorse rispetto alla creazione di contenitori. | I contenitori includono l'applicazione e tutte le relative dipendenze. Condividono tuttavia il kernel del sistema operativo con altri contenitori, in esecuzione come processi isolati nello spazio utente nel sistema operativo host. Tranne che nei contenitori Hyper-V, in cui ogni contenitore viene eseguito all'interno di una macchina virtuale speciale per contenitore. |

**Figura 2-3**. Confronto tra macchine virtuali tradizionali e contenitori Docker

Per le macchine virtuali, sono disponibili tre livelli di base nel server host, dal basso verso l'alto: infrastruttura, sistema operativo host e un hypervisor. Ogni macchina virtuale ha inoltre un proprio sistema operativo e tutte le librerie necessarie. Per Docker, il server host prevede solo l'infrastruttura e il sistema operativo, ma anche il motore del contenitore, che mantiene il contenitore isolato, ma che condivide i servizi di base del sistema operativo.

Poiché i contenitori richiedono un numero molto ridotto di risorse, ad esempio non necessitano di un sistema operativo completo, sono facili da distribuire e si avviano rapidamente. In questo modo è possibile ottenere un aumento della densità, vale a dire che è possibile eseguire più servizi nella stessa unità hardware, riducendo i costi.

Come effetto collaterale dell'esecuzione sullo stesso kernel, si ottiene un isolamento minore rispetto alle macchine virtuali.

L'obiettivo principale di un'immagine è rendere l'ambiente (dipendenze) uguale su distribuzioni diverse. Questo significa che è possibile eseguirne il debug nel computer corrente e quindi distribuirla in un altro computer con lo stesso ambiente garantito.

Un'immagine del contenitore consente di creare un pacchetto di app o servizi e distribuirlo in modo affidabile e riproducibile. Si potrebbe dire che Docker non è solo una tecnologia, ma anche una filosofia e un processo.

Quando si usa Docker, gli sviluppatori Docker non diranno mai "Funziona sul mio computer, perché non in produzione?" Potranno solo dire "È in esecuzione in Docker", perché l'applicazione Docker inserita in un pacchetto può essere eseguita in qualsiasi ambiente Docker supportato e viene eseguita nel modo previsto in tutte le destinazioni di distribuzione (ad esempio, sviluppo, controllo qualità, staging e produzione).

## <a name="a-simple-analogy"></a>Una semplice analogia

Forse una semplice analogia può aiutare a comprendere a fondo il concetto di base di Docker.

Torniamo per qualche istante agli anni '50. Non esistevano elaboratori di testo e quasi ovunque venivano usate le fotocopiatrici.

Si immagini di dover distribuire rapidamente un numero elevato di lettere, ovvero di spedirle ai clienti, usando carta e buste, e di recapitarle fisicamente all'indirizzo di ogni cliente perché la posta elettronica non esisteva.

A un certo punto ci si rende conto che le lettere sono semplicemente composte da una lunga serie di paragrafi, che vengono presi e combinati in base alle esigenze e allo scopo della lettera e pertanto si progetta un sistema per distribuire le lettere rapidamente, aspettandosi un incremento notevole.

Il sistema è semplice:

1. Si inizia con un blocco di fogli trasparenti ognuno dei quali contiene un paragrafo.

2. Per distribuire una serie di lettere, si prendono i fogli con i paragrafi necessari, quindi li si dispone e li si allinea in modo da poterli leggere agevolmente.

3. Infine, si inserisce il blocco nella fotocopiatrice e si premere Start per ottenere tutte le lettere necessarie.

Questa è in sostanza l'idea alla base di Docker.

In Docker ogni livello è il set di modifiche che si verificano nel file system dopo l'esecuzione di un comando, ad esempio, l'installazione di un programma.

Quando dunque si esamina il file system dopo che il livello è stato copiato, vengono visualizzati tutti i file, incluso il livello quando il programma è stato installato.

Un'immagine può essere considerata come un disco rigido di sola lettura ausiliario pronto per essere installato in "computer" in cui è già installato il sistema operativo.

Allo stesso modo, un contenitore può essere considerato come il "computer" con il disco rigido dell'immagine installato. Il contenitore, proprio come un computer, può essere acceso o spento.

>[!div class="step-by-step"]
>[Precedente](index.md)
>[Successivo](docker-terminology.md)
