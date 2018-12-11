---
title: Terminologia di Docker
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.openlocfilehash: 1efb2fa567bd452f0a0a5ee5afb6f759511e4145
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53151310"
---
# <a name="docker-terminology"></a>Terminologia di Docker

In questa sezione elenca i termini e definizioni con cui è necessario acquisire familiarità con prima di analizzare più profondo Docker (per altre definizioni, vedere l'ampia [glossario](https://docs.docker.com/glossary/) fornito da Docker a <https://docs.docker.com/glossary/>:

-   **Immagine del contenitore** un pacchetto con tutte le dipendenze e le informazioni necessarie per creare un contenitore. Un'immagine comprende tutte le dipendenze (ad esempio i framework) nonché la distribuzione e configurazione da usare dal runtime del contenitore. In genere, un'immagine deriva da più immagini di base che sono i livelli impilati uno sopra l'altro per formare il sistema di file del contenitore. Un'immagine non è modificabile dopo che è stato creato.

-   **Contenitore** un'istanza di un'immagine Docker. Un contenitore rappresenta un runtime per una singola applicazione, processo o del servizio. È costituito il contenuto di un'immagine Docker, un ambiente di runtime e un set di istruzioni standard. Quando si ridimensiona un servizio, si creano più istanze di un contenitore dalla stessa immagine oppure In alternativa, un processo batch può creare più contenitori dalla stessa immagine, passando parametri diversi a ogni istanza.

-   **Tag** contrassegno o etichetta che è possibile applicare alle immagini in modo da possono identificare immagini diverse o versioni della stessa immagine (a seconda del numero di versione o l'ambiente di destinazione).

-   **Dockerfile** un file di testo contenente istruzioni su come creare un'immagine Docker.

-   **Compilare** azione di compilazione di un'immagine del contenitore basata sulle informazioni e contesto forniti dal relativo documento Dockerfile, nonché i file aggiuntivi nella cartella in cui l'immagine viene creata. È possibile compilare le immagini usando il comando Docker docker build.

-   **Repository (noto anche come repository)** una raccolta di immagini Docker correlate, etichettate con un tag che indica la versione dell'immagine. Alcuni repository contengono più varianti di un'immagine specifica, ad esempio un'immagine contenente gli SDK (più pesanti), un'immagine contenente solo i Runtime (più leggeri) e così via. Tali varianti possono essere contrassegnate con i tag. Un singolo repository può contenere varianti di piattaforme, ad esempio un'immagine Linux e un'immagine di Windows.

-   **Registro di sistema** un servizio che fornisce l'accesso ai repository. Il registro predefinito per la maggior parte delle immagini pubbliche è l'[Hub Docker](https://hub.docker.com/), di proprietà di Docker a livello di organizzazione. Un registro contiene in genere i repository di più team. Spesso le aziende hanno registri privati in cui archiviare e gestire le immagini che hanno creato. *Registro contenitori di Azure* è un altro esempio.

-   **Hub docker** registro pubblico in cui caricare le immagini e usarle. L'hub Docker fornisce l'hosting di immagini Docker, registri pubblici o privati, trigger e webhook di compilazione e integrazione con GitHub e Bitbucket.

-   **Registro contenitori di Azure** una risorsa pubblica per l'utilizzo di immagini Docker e dei relativi componenti in Azure. Fornisce un registro vicino alle distribuzioni in Azure e offre il controllo sugli accessi, tramite i gruppi e le autorizzazioni di Azure Active Directory.

-   **Docker Trusted Registry (DTR)** servizio di registro di Docker (di Docker) che è possibile installare in locale in modo che si trova all'interno di Data Center e rete dell'organizzazione. È una soluzione pratica per le immagini private che devono essere gestite all'interno dell'azienda. Docker Trusted Registry è incluso nel prodotto Docker Datacenter. Per altre informazioni, visitare [ https://docs.docker.com/docker-trusted-registry/overview/ ](https://docs.docker.com/docker-trusted-registry/overview/).

-   **Docker Community Edition (CE)** strumenti di sviluppo per Windows e macOS per la compilazione, esecuzione e il test dei contenitori in locale. Docker CE per Windows offre ambienti di sviluppo per contenitori Linux e Windows. L'host Linux Docker in Windows si basa su un [Hyper-V](https://www.microsoft.com/en-us/server-cloud/solutions/virtualization.aspx) della macchina virtuale. L'host per Contenitori Windows è direttamente basato su Windows. Docker CE per Mac è basato sul framework Hypervisor di Apple e la [hypervisor xhyve](https://github.com/mist64/xhyve), che fornisce una macchina virtuale host Linux Docker in Mac OS X. Docker CE per Windows e per Mac sostituisce Docker Toolbox, basato su Oracle VirtualBox.

-   **Docker Enterprise Edition (EE)** una versione di scala aziendale degli strumenti di Docker per lo sviluppo di Linux e Windows.

-   **Comporre** uno strumento da riga di comando e YAML formato di file con i metadati per definire ed eseguire applicazioni multicontenitore. Si definisce una singola applicazione in base a più immagini con uno o più file YML che possono eseguire l'override dei valori a seconda dell'ambiente. Dopo aver creato le definizioni, è possibile distribuire l'intera applicazione multicontenitore con un singolo comando (docker-compose backup) che crea un contenitore per ogni immagine nell'host Docker.

-   **Cluster** una raccolta di host Docker esposta come se fossero un singolo host Docker virtuale, in modo che l'applicazione può essere ridimensionata per più istanze dei servizi distribuite tra più host all'interno del cluster. È possibile creare cluster Docker con Docker Swarm, Mesosphere DC/OS, Kubernetes e Azure Service Fabric. Se si usa Docker Swarm per gestire un cluster, si farà normalmente riferimento al cluster chiamandolo *swarm* anziché cluster.

-   **Agente di orchestrazione** uno strumento che semplifica la gestione dei cluster e l'host Docker. Usando gli agenti di orchestrazione, è possibile gestire le immagini, contenitori e host tramite un'interfaccia della riga di comando o un'interfaccia utente grafica. È possibile gestire le reti di contenitori, le configurazioni, il bilanciamento del carico, l'individuazione di servizi, la disponibilità elevata, la configurazione dell'host Docker e altro ancora. Un agente di orchestrazione è responsabile dell'esecuzione, della distribuzione, del ridimensionamento e della correzione dei carichi di lavoro in una raccolta di nodi. In genere, i prodotti per l'agente di orchestrazione sono gli stessi che forniscono l'infrastruttura cluster, ad esempio Mesosphere DC/OS, Kubernetes, Docker Swarm e Azure Service Fabric.

>[!div class="step-by-step"]
>[Precedente](what-is-docker.md)
>[Successivo](docker-containers-images-and-registries.md)