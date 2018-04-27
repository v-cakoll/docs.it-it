---
title: Contenitori, immagini e registri Docker
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8ba0cd3323467e07a33ffd4083e390d57fdce7ff
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="docker-containers-images-and-registries"></a>Contenitori, immagini e registri Docker

Quando si usa Docker, creerai un'app o un servizio e un pacchetto e le relative dipendenze in un'immagine contenitore. Un'immagine è una rappresentazione statica dell'app o del servizio, della relativa configurazione e delle dipendenze.

Per eseguire l'applicazione o servizio, viene creata un'istanza di immagine dell'applicazione per creare un contenitore, che verrà eseguito nell'host Docker. I contenitori vengono inizialmente testati in un PC o in un ambiente di sviluppo.

Archiviare le immagini in un registro di sistema, che funziona come una libreria di immagini. È necessario un registro di sistema durante la distribuzione in orchestrators di produzione. Docker mantiene un registro pubblico tramite l'[hub Docker](https://hub.docker.com/). Altri fornitori offrono registri per diverse raccolte di immagini. In alternativa, le aziende possono gestire un registro privato locale per le proprie immagini Docker.

Figura 1-4 viene illustrato come le immagini e i registri in Docker correlati ad altri componenti. Mostra inoltre le varie offerte dei fornitori per i registri.

![](./media/image4.png)

Figura 1-4: tassonomia di concetti e termini di Docker

Inserendo le immagini in un registro di sistema, è possibile archiviare i bit di applicazione statico e non modificabile, incluse tutte le relative dipendenze, un livello di framework. È quindi possibile modificare la versione e distribuire le immagini in più ambienti e pertanto costituiscono un'unità di distribuzione uniforme.

Registri di immagine privata ospitata in locale o nel cloud, sono consigliate per le situazioni seguenti:

-   Le immagini non devono essere condivise pubblicamente per motivi di riservatezza.

-   Si desidera una latenza di rete minima tra le immagini e l'ambiente di distribuzione scelto. Ad esempio, se l'ambiente di produzione Azure, si vorrà memorizzare le immagini nel Registro di sistema contenitore di Azure in modo che la latenza di rete sarà minima. Allo stesso modo, se l'ambiente di produzione è ospitato in locale, è consigliabile che il registro Docker Trusted Registry sia disponibile nella stessa rete locale.

>[!div class="step-by-step"]
[Precedente] (docker-terminology.md) [Avanti] (Docker-applicazione-del ciclo di vita/index.md)
