---
title: Contenitori, immagini e registri Docker
description: Informazioni sul ruolo chiave dei registri nella modalità di distribuzione delle applicazioni da parte di Docker.
ms.date: 02/15/2019
ms.openlocfilehash: bfef21cab7be89abaf33b89366d7cff2115a7cc6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72770922"
---
# <a name="docker-containers-images-and-registries"></a>Contenitori, immagini e registri Docker

Quando si usa Docker, si crea un'app o un servizio e si crea un pacchetto contenente l'app o il servizio e le relative dipendenze in un'immagine del contenitore. Un'immagine è una rappresentazione statica dell'app o del servizio, della relativa configurazione e delle dipendenze.

Per eseguire l'app o il servizio, si crea un'istanza dell'immagine dell'app per creare un contenitore che verrà eseguito nell'host Docker. I contenitori vengono inizialmente testati in un PC o in un ambiente di sviluppo.

Le immagini vengono archiviate in un Registro di sistema che funge da libreria di immagini. È necessario un registro durante la distribuzione negli agenti di orchestrazione di produzione. Docker mantiene un registro pubblico tramite [Docker Hub](https://hub.docker.com/). Altri fornitori offrono registri per diverse raccolte di immagini, incluso il [Registro Azure Container](https://azure.microsoft.com/services/container-registry/). In alternativa, le aziende possono gestire un registro privato locale per le proprie immagini Docker.

La figura 1-4 mostra la relazione tra le immagini e i registri in Docker e altri componenti. Mostra inoltre le varie offerte dei fornitori per i registri.

![Diagramma che mostra la tassonomia di base in Docker.](./media/docker-containers-images-and-registries/taxonomy-docker-terms-concepts.png)

**Figura 1-4**. Tassonomia dei termini e dei concetti di Docker

il registro è paragonabile a una libreria in cui le immagini sono archiviate e disponibili per il pull per la creazione di contenitori per eseguire servizi o app Web. Sono disponibili registri Docker privati in locale e nel cloud pubblico. L'hub Docker è un registro pubblico gestito da Docker. Oltre a Docker Trusted Registry, una soluzione di livello aziendale, Azure offre il Registro Azure Container. Anche AWS, Google e altri hanno registri contenitori.

L'inserimento delle immagini in un registro permette di archiviare bit di applicazioni statici e immutabili, incluse tutte le dipendenze, a livello di framework. È quindi possibile creare diverse versioni delle immagini e distribuirle in più ambienti per offrire un'unità di distribuzione coerente.

I registri di immagini privati, ospitati in locale o nel cloud, sono consigliati nei casi seguenti:

- Le immagini non devono essere condivise pubblicamente per motivi di riservatezza.

- Si desidera una latenza di rete minima tra le immagini e l'ambiente di distribuzione scelto. Ad esempio se l'ambiente di produzione è Azure, è possibile archiviare le immagini nel [Registro Azure Container](https://azure.microsoft.com/services/container-registry/) per ridurre al minimo la latenza di rete. Allo stesso modo, se l'ambiente di produzione è ospitato in locale, è consigliabile che il registro Docker Trusted Registry sia disponibile nella stessa rete locale.

>[!div class="step-by-step"]
>[Successivo](docker-terminology.md)
>[precedente](road-to-modern-applications-based-on-containers.md)
