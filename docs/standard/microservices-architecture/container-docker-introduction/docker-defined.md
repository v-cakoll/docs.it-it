---
title: "Che cos'è Docker?"
description: "Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Che cos'è Docker?"
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: aa9cb379628fa91e5dc5b1b529f92db98fa59305
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="what-is-docker"></a>Che cos'è Docker?

[Docker](https://www.docker.com/) è un [progetto open source](https://github.com/docker/docker) per automatizzare la distribuzione di applicazioni come portabile, autosufficiente contenitori che è possibile eseguire nel cloud o locale. Docker è anche un [società](https://www.docker.com/) che Alza di livello e si evolve questa tecnologia. Docker funziona in collaborazione con fornitori di Windows, inclusi Microsoft di cloud, Linux e.

![](./media/image2.png)

**Figura 2-2**. Docker consente di distribuire contenitori di tutti i livelli del cloud ibrido

Contenitori di immagini docker vengono eseguiti in modo nativo in Linux e Windows. Immagini di Windows eseguire solo negli host di Windows e Linux immagini eseguite solo su host Linux. L'host è un server o una macchina virtuale.

È possibile sviluppare in Windows, Linux o Mac OS. Il computer di sviluppo viene eseguito un host Docker in cui sono distribuite le immagini Docker, tra cui l'app e le relative dipendenze. In Linux o Mac OS, utilizzare un host Docker Linux in base e creare immagini solo per i contenitori di Linux. (In macOS è possibile modificare il codice o eseguire l'interfaccia CLI di Docker, ma al momento della redazione del presente documento, i contenitori non vengono eseguiti direttamente in macOS.) In Windows è possibile creare immagini per i contenitori di Windows o Linux.

In Windows o Mac OS, [Docker Community Edition (CE)](https://www.docker.com/community-edition) ospita contenitori in un ambiente di sviluppo e fornisce gli strumenti di sviluppo aggiuntive. [Docker Enterprise Edition (EE)](https://www.docker.com/enterprise-edition) viene usato dai team IT che compila, spedire ed eseguire applicazioni business-critical di grandi dimensioni. ~ La macchina virtuale necessaria (host Docker) per ospitare i contenitori di installare entrambi i prodotti. ~ 

[Contenitori di Windows](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview) funzionano con due tipi di runtime:

-   Contenitori di Windows Server offrono l'isolamento dell'applicazione attraverso una tecnologia di isolamento dei processi e dello spazio dei nomi. Un contenitore di Windows Server condivide un kernel con l'host contenitore e tutti i contenitori in esecuzione nell'host.

-   I contenitori di Hyper-V si espandono l'isolamento fornito dai contenitori di Windows Server eseguendo ciascun contenitore in una macchina virtuale altamente ottimizzata. In questa configurazione il kernel dell'host contenitore non viene condiviso con i contenitori di Hyper-V, che fornisce un migliore isolamento. Consente di contenitori di Hyper-V non attendibili e *ostile multi-tenant* applicazioni da eseguire nello stesso host. Contenitori di Hyper-V hanno un po' meno efficienza in tempi di avvio e la densità più contenitori di Windows Server.

Le immagini per questi contenitori vengono create e funzionano allo stesso modo. Differiscono nel modo in cui viene creato il contenitore. Per informazioni dettagliate, vedere [contenitori di Hyper-V](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview).

## <a name="comparing-docker-containers-with-virtual-machines"></a>Confronto tra contenitori di Docker con le macchine virtuali

Figura 2-3 viene illustrato un confronto tra le macchine virtuali e Docker contenitori.

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  **Macchine virtuali****contenitori di Docker** 
                                                                                                                                                                                        
  ![](./media/image3.png)                                                                                                                                ![](./media/image4.png)
                                                                                                                                                                                        
  Macchine virtuali includono l'applicazione, le librerie necessarie o i file binari e un sistema operativo completo. Virtualizzazione completa richiede più risorse di creazione dei contenitori. I contenitori includono l'applicazione e tutte le relative dipendenze. Tuttavia, i contenitori condividono kernel del sistema operativo con gli altri contenitori. Contenitori vengono eseguiti come processi isolati nello spazio utente nel sistema operativo host. Tranne che in contenitori di Hyper-V in ogni contenitore viene eseguito all'interno di una speciale macchina virtuale per ogni contenitore.
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**Figura 2-3**. Confronto tra le macchine virtuali tradizionali ai contenitori di Docker

Poiché i contenitori richiedono molto meno risorse (ad esempio, non richiedono un sistema operativo completo), avvio rapido e facili da distribuire. Basso utilizzo delle risorse consente maggiore densità. È possibile eseguire più servizi nella stessa unità di hardware e ridurre i costi.

Gli stessi risultati del kernel in meno isolamento rispetto a forniscono le macchine virtuali in esecuzione.

L'obiettivo principale di un'immagine è che rende l'ambiente (dipendenze) uguali tra le diverse distribuzioni. Ciò significa che è possibile eseguire il debug nel computer e quindi distribuirla in un altro computer con lo stesso ambiente garantito.

Un'immagine contenitore è un modo per un'app o un servizio del pacchetto e distribuirlo in modo affidabile e riproducibile. È possibile specificare che Docker sia non solo una tecnologia, ma anche una filosofia e un processo.

Gli sviluppatori di docker non ad esempio, "Funziona nel computer, non vengono visualizzati nell'ambiente di produzione?" Si dice, "Viene eseguito in Docker". App in pacchetto docker può essere eseguita in qualsiasi ambiente supportato da Docker. App in pacchetto docker eseguire in modo coerente in tutte le destinazioni di distribuzione (sviluppo, QA, gestione temporanea, produzione).

>[!div class="step-by-step"]
[Precedente] [Avanti] (docker terminology.md) (index.md)
