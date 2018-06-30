---
title: Contenitori, immagini e registri Docker
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: ff5a1f3e4b09ac9f7ea600d3f127523b96fcce55
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106363"
---
# <a name="docker-containers-images-and-registries"></a>Contenitori, immagini e registri Docker

Quando si usa Docker, creerai un'app o un servizio e un pacchetto e le relative dipendenze in un'immagine contenitore. Un'immagine è una rappresentazione statica dell'app o del servizio, della relativa configurazione e delle dipendenze.

Per eseguire l'app o il servizio, viene creata un'istanza di immagini dell'app per creare un contenitore, che verrà eseguito nell'host Docker. I contenitori vengono inizialmente testati in un PC o in un ambiente di sviluppo.

Archiviare le immagini in un registro di sistema, che funziona come una libreria di immagini. È necessario un registro di sistema durante la distribuzione in orchestrators di produzione. Docker mantiene un registro pubblico tramite l'[hub Docker](https://hub.docker.com/). Altri fornitori offrono registri per diverse raccolte di immagini. In alternativa, le aziende possono gestire un registro privato locale per le proprie immagini Docker.

Figura 1-4 mostra le immagini e i registri in Docker correlazione tra gli altri componenti. Mostra inoltre le varie offerte dei fornitori per i registri.

![](./media/image4.png)

Figura 1-4: tassonomia di concetti e termini di Docker

Inserendo le immagini in un registro di sistema, è possibile archiviare bit statico e non modificabile l'applicazione, incluse tutte le dipendenze, un livello di framework. È quindi possibile modificare la versione e distribuire le immagini in più ambienti e pertanto costituiscono un'unità di distribuzione coerente.

I registri delle immagini personali, ospitato in locale o nel cloud, sono consigliati per le situazioni seguenti:

-   Le immagini non devono essere condivise pubblicamente per motivi di riservatezza.

-   Si desidera una latenza di rete minima tra le immagini e l'ambiente di distribuzione scelto. Ad esempio, se l'ambiente di produzione Azure, è possibile archiviare le immagini nel Registro di sistema contenitore di Azure in modo che la latenza di rete sarà minima. Allo stesso modo, se l'ambiente di produzione è ospitato in locale, è consigliabile che il registro Docker Trusted Registry sia disponibile nella stessa rete locale.

>[!div class="step-by-step"]
[Precedente](docker-terminology.md)
[Successivo](Docker-application-lifecycle/index.md)
