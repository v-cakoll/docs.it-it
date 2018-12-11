---
title: Contenitori, immagini e registri Docker
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: af235280c985d20f9e6a2ee6096edbe6c3aad63a
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53142749"
---
# <a name="docker-containers-images-and-registries"></a>Contenitori, immagini e registri Docker

Quando si usa Docker, si crea un'app o servizio e un pacchetto e le relative dipendenze in un'immagine del contenitore. Un'immagine è una rappresentazione statica dell'app o del servizio, della relativa configurazione e delle dipendenze.

Per eseguire l'app o il servizio, si crea un'istanza dell'immagine dell'app per creare un contenitore che verrà eseguito nell'host Docker. I contenitori vengono inizialmente testati in un PC o in un ambiente di sviluppo.

Archiviare immagini in un registro di sistema, che agisce come una raccolta di immagini. È necessario un registro di sistema durante la distribuzione di agenti di orchestrazione di produzione. Docker mantiene un registro pubblico tramite l'[hub Docker](https://hub.docker.com/). Altri fornitori offrono registri per diverse raccolte di immagini. In alternativa, le aziende possono gestire un registro privato locale per le proprie immagini Docker.

Figura 1-4 viene illustrato come immagini e i registri in Docker correlati ad altri componenti. Mostra inoltre le varie offerte dei fornitori per i registri.

![](./media/image4.png)

Figura 1-4: Tassonomia dei termini e dei concetti di Docker

Inserendo le immagini in un registro di sistema, è possibile archiviare bit di applicazioni statici e immutabili, incluse tutte le relative dipendenze, a livello di framework. È quindi possibile modificare la versione e distribuire le immagini in più ambienti e quindi di fornire un'unità di distribuzione coerente.

Registri di immagini privati, ospitati in locale o nel cloud, sono consigliati per le situazioni seguenti:

-   Le immagini non devono essere condivise pubblicamente per motivi di riservatezza.

-   Si desidera una latenza di rete minima tra le immagini e l'ambiente di distribuzione scelto. Ad esempio, se l'ambiente di produzione è Azure, probabilmente desidera archiviare le immagini nel registro contenitori di Azure in modo che la latenza di rete sarà minima. Allo stesso modo, se l'ambiente di produzione è ospitato in locale, è consigliabile che il registro Docker Trusted Registry sia disponibile nella stessa rete locale.

>[!div class="step-by-step"]
>[Precedente](docker-terminology.md)
>[Successivo](Docker-application-lifecycle/index.md)