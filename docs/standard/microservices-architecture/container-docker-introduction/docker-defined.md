---
title: Che cos'è Docker?
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Che cos'è Docker?
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 06dd5199b8dbc42ce3e9ae35bc5c3673d01cb4de
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106801"
---
# <a name="what-is-docker"></a>Che cos'è Docker?

[Docker](https://www.docker.com/) è un [progetto open source](https://github.com/docker/docker) per automatizzare la distribuzione di app come contenitori portabili e autosufficienti che possono essere eseguiti nel cloud o in locale. Docker è anche un'[azienda](https://www.docker.com/) che promuove questa tecnologia e ne guida l'evoluzione. Docker collabora con i fornitori di Windows, Linux e servizi cloud, inclusa Microsoft.

![](./media/image2.png)

**Figura 2-2**. Docker distribuisce contenitori a tutti i livelli del cloud ibrido

I contenitori di immagini Docker vengono eseguiti in modo nativo in Linux e Windows. Le immagini Windows vengono eseguite solo negli host Windows e le immagini Linux solo negli host Linux. L'host è un server o una macchina virtuale.

È possibile sviluppare in Windows, Linux o macOS. Il computer di sviluppo esegue un host Docker in cui vengono distribuite le immagini Docker, inclusa l'app e le relative dipendenze. In Linux o macOS, si usa un host Docker basato su Linux che può creare immagini solo per i contenitori Linux. In macOS è possibile modificare il codice o eseguire l'interfaccia della riga di comando di Docker, ma al momento della stesura di questo documento, non è possibile eseguire i contenitori direttamente in macOS. In Windows è possibile creare le immagini sia per i contenitori Linux che per i contenitori Windows.

In Windows o in macOS [Docker Community Edition (CE)](https://www.docker.com/community-edition) ospita i contenitori in un ambiente di sviluppo e offre strumenti di sviluppo aggiuntivi. [Docker Enterprise Edition (EE)](https://www.docker.com/enterprise-edition) è invece usato dai team IT che compilano, distribuiscono ed eseguono applicazioni business-critical di grandi dimensioni. ~Entrambi i prodotti installano la macchina virtuale necessaria (host Docker) per l'hosting dei contenitori.~ 

I [contenitori Windows](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview) funzionano con due tipi di runtime:

-   I contenitori Windows Server offrono l'isolamento dell'applicazione tramite una tecnologia di isolamento dei processi e dello spazio dei nomi. Un contenitore Windows Server condivide un kernel con l'host del contenitore e con tutti i contenitori in esecuzione nell'host.

-   I contenitori Hyper-V espandono l'isolamento fornito dai contenitori Windows Server tramite l'esecuzione di ogni contenitore in una macchina virtuale con ottimizzazione elevata. In questa configurazione, il kernel dell'host dei contenitori non è condiviso con i contenitori Hyper-V per fornire un isolamento migliore. I contenitori Hyper-V consentono l'esecuzione di applicazioni non attendibili e *multi-tenant ostili* nello stesso host. I contenitori Hyper-V presentano tempi di avvio e densità meno efficienti rispetto ai contenitori Windows Server.

Le immagini per questi contenitori vengono create e funzionano nello stesso modo. La differenza sta nella modalità di creazione del contenitore. Per informazioni dettagliate, vedere [Contenitori Hyper-V](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview).

## <a name="comparing-docker-containers-with-virtual-machines"></a>Confronto tra contenitori Docker e macchine virtuali

La figura 2-3 mostra un confronto tra macchine virtuali e contenitori Docker.

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  **Macchine virtuali**                                                                                                                                                                  **Contenitori Docker**
                                                                                                                                                                                        
  ![](./media/image3.png)                                                                                                                                ![](./media/image4.png)
                                                                                                                                                                                        
  Le macchine virtuali includono l'applicazione, le librerie o i file binari necessari e un sistema operativo guest completo. La virtualizzazione completa richiede più risorse rispetto alla creazione di contenitori. I contenitori includono l'applicazione e tutte le relative dipendenze. Tuttavia, i contenitori condividono il kernel del sistema operativo con altri contenitori. I contenitori vengono eseguiti come processi isolati nello spazio utente nel sistema operativo host. Tranne che nei contenitori Hyper-V, in cui ogni contenitore viene eseguito all'interno di una macchina virtuale speciale per contenitore.
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**Figura 2-3**. Confronto tra macchine virtuali tradizionali e contenitori Docker

Poiché i contenitori richiedono un numero molto ridotto di risorse, ad esempio non necessitano di un sistema operativo completo, si avviano rapidamente e sono facili da distribuire. L'utilizzo ridotto delle risorse consente una densità più elevata. È possibile eseguire più servizi nella stessa unità hardware e ridurre i costi.

L'esecuzione nello stesso kernel determina un isolamento minore rispetto a quello fornito dalle macchine virtuali.

L'obiettivo principale di un'immagine è rendere l'ambiente (dipendenze) uguale su distribuzioni diverse. Questo significa che è possibile eseguirne il debug nel computer corrente e quindi distribuirla in un altro computer con lo stesso ambiente garantito.

Un'immagine del contenitore consente di creare un pacchetto di app o servizi e distribuirlo in modo affidabile e riproducibile. Si potrebbe dire che Docker non è solo una tecnologia, ma anche una filosofia e un processo.

Gli sviluppatori Docker non dicono "Funziona sul mio computer, perché non in produzione?" Dicono "È in esecuzione in Docker." Le app in pacchetti per Docker possono essere eseguite in qualsiasi ambiente Docker supportato. Le app in pacchetti per Docker vengono eseguite in modo coerente in tutte le destinazioni di distribuzione, ovvero sviluppo, controllo qualità, staging, produzione.

>[!div class="step-by-step"]
[Precedente](index.md)
[Successivo](docker-terminology.md)
