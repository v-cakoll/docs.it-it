---
title: Contenitori, immagini e registri Docker
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Contenitori, immagini e registri Docker
ms.date: 08/31/2018
ms.openlocfilehash: 3b643a3bf4ca3ce1b8ba3fc40cd2f3ad8bbe5ffb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "73737780"
---
# <a name="docker-containers-images-and-registries"></a>Contenitori, immagini e registri Docker

Quando uno sviluppatore usa Docker, crea un app o un servizio e crea un pacchetto contenente l'app o il servizio e le relative dipendenze in un'immagine del contenitore. Un'immagine è una rappresentazione statica dell'app o del servizio, della relativa configurazione e delle dipendenze.

Per eseguire l'app o il servizio, si crea un'istanza dell'immagine dell'app per creare un contenitore che verrà eseguito nell'host Docker. I contenitori vengono inizialmente testati in un PC o in un ambiente di sviluppo.

Gli sviluppatori devono archiviare le immagini in un registro, che funge da libreria di immagini e che è necessario per la distribuzione negli agenti di orchestrazione di produzione. Docker mantiene un registro pubblico tramite [Docker Hub](https://hub.docker.com/). Altri fornitori offrono registri per diverse raccolte di immagini, incluso il [Registro Azure Container](https://azure.microsoft.com/services/container-registry/). In alternativa, le aziende possono gestire un registro privato locale per le proprie immagini Docker.

La figura 2-4 mostra la relazione tra le immagini e i registri in Docker con altri componenti. Mostra inoltre le varie offerte dei fornitori per i registri.

![Diagramma che mostra la tassonomia di base in Docker.](./media/docker-containers-images-registries/taxonomy-of-docker-terms-and-concepts.png)

**Figura 2-4**. Tassonomia dei termini e dei concetti di Docker

il registro è paragonabile a una libreria in cui le immagini sono archiviate e disponibili per il pull per la creazione di contenitori per eseguire servizi o app Web. Sono disponibili registri Docker privati in locale e nel cloud pubblico. L'hub Docker è un registro pubblico gestito da Docker. Oltre a Docker Trusted Registry, una soluzione di livello aziendale, Azure offre il Registro Azure Container. Anche AWS, Google e altri hanno registri contenitori.

L'inserimento delle immagini in un registro permette di archiviare bit di applicazioni statici e immutabili, incluse tutte le dipendenze a livello di framework. È quindi possibile creare diverse versioni delle immagini e distribuirle in più ambienti per fornire un'unità di distribuzione coerente.

I registri di immagini privati, ospitati in locale o nel cloud, sono consigliati nei casi seguenti:

- Le immagini non devono essere condivise pubblicamente per motivi di riservatezza.

- Si desidera una latenza di rete minima tra le immagini e l'ambiente di distribuzione scelto. Se ad esempio l'ambiente di produzione è il cloud di Azure, è consigliabile archiviare le immagini nel [Registro Azure Container](https://azure.microsoft.com/services/container-registry/) per una latenza di rete minima. Allo stesso modo, se l'ambiente di produzione è ospitato in locale, è consigliabile che il registro Docker Trusted Registry sia disponibile nella stessa rete locale.

>[!div class="step-by-step"]
>[Successivo](docker-terminology.md)
>[precedente](../net-core-net-framework-containers/index.md)
