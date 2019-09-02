---
title: Contenitori, immagini e registri Docker
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Contenitori, immagini e registri Docker
ms.date: 08/31/2018
ms.openlocfilehash: 520f8d4d54f1fdd227ff9a1e88660b62e75f927f
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68674898"
---
# <a name="docker-containers-images-and-registries"></a>Contenitori, immagini e registri Docker

Quando uno sviluppatore usa Docker, crea un app o un servizio e crea un pacchetto contenente l'app o il servizio e le relative dipendenze in un'immagine del contenitore. Un'immagine è una rappresentazione statica dell'app o del servizio, della relativa configurazione e delle dipendenze.

Per eseguire l'app o il servizio, si crea un'istanza dell'immagine dell'app per creare un contenitore che verrà eseguito nell'host Docker. I contenitori vengono inizialmente testati in un PC o in un ambiente di sviluppo.

Gli sviluppatori devono archiviare le immagini in un registro, che funge da libreria di immagini e che è necessario per la distribuzione negli agenti di orchestrazione di produzione. Docker mantiene un registro pubblico tramite [Docker Hub](https://hub.docker.com/). Altri fornitori offrono registri per diverse raccolte di immagini, incluso il [Registro Azure Container](https://azure.microsoft.com/services/container-registry/). In alternativa, le aziende possono gestire un registro privato locale per le proprie immagini Docker.

La figura 2-4 mostra la relazione tra le immagini e i registri in Docker con altri componenti. Mostra inoltre le varie offerte dei fornitori per i registri.

![Tassonomia di base in Docker: il registro è paragonabile a una libreria in cui le immagini sono archiviate e disponibili per il pull per la creazione di contenitori per eseguire servizi o app Web. Sono disponibili registri Docker privati in locale e nel cloud pubblico. L'hub Docker è un registro pubblico gestito da Docker. Oltre a Docker Trusted Registry, una soluzione di livello aziendale, Azure offre il Registro Azure Container. Anche AWS, Google e altri hanno registri contenitori.](./media/image5.PNG)

**Figura 2-4**. Tassonomia dei termini e dei concetti di Docker

L'inserimento delle immagini in un registro permette di archiviare bit di applicazioni statici e immutabili, incluse tutte le dipendenze a livello di framework. È quindi possibile creare diverse versioni delle immagini e distribuirle in più ambienti per fornire un'unità di distribuzione coerente.

I registri di immagini privati, ospitati in locale o nel cloud, sono consigliati nei casi seguenti:

- Le immagini non devono essere condivise pubblicamente per motivi di riservatezza.

- Si desidera una latenza di rete minima tra le immagini e l'ambiente di distribuzione scelto. Se ad esempio l'ambiente di produzione è il cloud di Azure, è consigliabile archiviare le immagini nel [Registro Azure Container](https://azure.microsoft.com/services/container-registry/) per una latenza di rete minima. Allo stesso modo, se l'ambiente di produzione è ospitato in locale, è consigliabile che il registro Docker Trusted Registry sia disponibile nella stessa rete locale.

>[!div class="step-by-step"]
>[Precedente](docker-terminology.md)
>[Successivo](../net-core-net-framework-containers/index.md)
