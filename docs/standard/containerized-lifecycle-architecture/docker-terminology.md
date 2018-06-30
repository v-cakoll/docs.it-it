---
title: Terminologia di Docker
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.openlocfilehash: 0b13f28f4314ef72fbcaffe894bf823486665d3f
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106097"
---
# <a name="docker-terminology"></a>Terminologia di Docker

Questa sezione sono elencati i termini e definizioni con cui è necessario acquisire familiarità prima di analizzare più approfondita Docker (per un'ulteriore definizioni, vedere esteso [glossario](https://docs.docker.com/glossary/) fornito da Docker in <https://docs.docker.com/glossary/>:

-   **Immagine contenitore** un pacchetto con tutte le dipendenze e le informazioni necessarie per creare un contenitore. Un'immagine include tutte le dipendenze (ad esempio, Framework) oltre a distribuzione e configurazione utilizzabile da un runtime del contenitore. In genere, un'immagine deriva da più immagini di base che sono livelli disposte in pila una sopra l'altro per formare il sistema di file del contenitore. Un'immagine non è modificabile dopo che è stato creato.

-   **Contenitore** un'istanza di un'immagine di Docker. Un contenitore rappresenta una fase di esecuzione per una singola applicazione, un processo o un servizio. È costituito il contenuto di un'immagine Docker, un ambiente di runtime e un set standard di istruzioni. Quando si ridimensiona un servizio, si creano più istanze di un contenitore dalla stessa immagine oppure In alternativa, un processo batch è possibile creare più contenitori dalla stessa immagine, il passaggio di parametri diversi per ogni istanza.

-   **Tag** un contrassegno o un'etichetta che è possibile applicare alle immagini in modo che possono essere identificate immagini differenti o le versioni della stessa immagine (a seconda del numero di versione o l'ambiente di destinazione).

-   **Dockerfile** un file di testo contenente istruzioni su come creare un'immagine Docker.

-   **Compilare** l'azione di compilazione di un'immagine contenitore in base alle informazioni e contesto fornito dal relativo Dockerfile, nonché file aggiuntivi nella cartella in cui l'immagine viene creata. È possibile compilare le immagini usando il comando di compilazione docker Docker.

-   **Repository (noto anche come repository)** una raccolta di immagini Docker correlate con etichettata con un tag che indica la versione dell'immagine. Alcuni archivi contengono più varianti di un'immagine specifica, ad esempio un'immagine che contiene gli SDK (più pesanti), un'immagine che contiene solo i Runtime (semplificati), e così via. Tali varianti possono essere contrassegnate con i tag. Un unico archivio può contenere le varianti della piattaforma, ad esempio un'immagine Linux e un'immagine di Windows.

-   **Registro di sistema** un servizio che fornisce l'accesso al repository. Il registro predefinito per la maggior parte delle immagini pubbliche è l'[Hub Docker](https://hub.docker.com/), di proprietà di Docker a livello di organizzazione. Un registro contiene in genere i repository di più team. Le società hanno spesso registri privati per archiviare e gestire le immagini che hanno creato. *Registro di sistema contenitore Azure* costituisce un altro esempio.

-   **Hub docker** un registro di sistema pubblico per il caricamento di immagini e utilizzarli. L'hub Docker fornisce l'hosting di immagini Docker, registri pubblici o privati, trigger e webhook di compilazione e integrazione con GitHub e Bitbucket.

-   **Registro di sistema contenitore di Azure** una risorsa pubblica per l'utilizzo di immagini Docker e i relativi componenti in Azure. Fornisce un registro vicino alle distribuzioni in Azure e offre il controllo sugli accessi, tramite i gruppi e le autorizzazioni di Azure Active Directory.

-   **Docker Trusted del Registro di sistema DTR ()** servizio Registro di sistema A Docker (da Docker) che è possibile installare in locale in modo che si trova all'interno di Data Center e di rete dell'organizzazione. È una soluzione pratica per le immagini private che devono essere gestite all'interno dell'azienda. Docker Trusted Registry è incluso nel prodotto Docker Datacenter. Per altre informazioni, visitare [ https://docs.docker.com/docker-trusted-registry/overview/ ](https://docs.docker.com/docker-trusted-registry/overview/).

-   **Docker Community Edition (CE)** gli strumenti di sviluppo per Windows e macOS per la creazione, esecuzione e il test dei contenitori in locale. Docker CE per Windows offre ambienti di sviluppo per contenitori Linux e Windows. L'host Linux Docker in Windows si basa su un [Hyper-V](https://www.microsoft.com/en-us/server-cloud/solutions/virtualization.aspx) macchina virtuale. L'host per Contenitori Windows è direttamente basato su Windows. Docker CE per Mac si basa su framework Hypervisor Apple e la [hypervisor xhyve](https://github.com/mist64/xhyve), che fornisce un host Linux Docker VM in Mac OS X. Docker CE per Windows e per Mac sostituisce della casella degli strumenti di Docker, che è basato su Oracle VirtualBox.

-   **Docker Enterprise Edition (EE)** una versione su larga scala degli strumenti di Docker per lo sviluppo di Linux e Windows.

-   **Comporre** uno strumento da riga di comando e YAML formato con i metadati per la definizione e multicontainer applicazioni in esecuzione. Si definisce una singola applicazione in base a più immagini con uno o più file YML che possono eseguire l'override dei valori a seconda dell'ambiente. Dopo aver creato le definizioni, è possibile distribuire l'intera applicazione multicontainer utilizzando un unico comando (docker-comporre backup) che crea un contenitore per ogni immagine dell'host Docker.

-   **Cluster** un insieme di host Docker esposte come se fossero un unico host Docker virtuale in modo che l'applicazione può essere scalato più istanze dei servizi distribuiti tra più host all'interno del cluster. È possibile creare cluster Docker tramite Docker Swarm Mesosphere DC/OS, Kubernetes e Azure Service Fabric. Se si usa Docker Swarm per gestire un cluster, si farà normalmente riferimento al cluster chiamandolo *swarm* anziché cluster.

-   **Orchestrator** uno strumento che semplifica la gestione di Docker host e cluster. Utilizza orchestrators, è possibile gestire le immagini, contenitori e gli host tramite CLI o un'interfaccia utente grafica. È possibile gestire le reti di contenitori, le configurazioni, il bilanciamento del carico, l'individuazione di servizi, la disponibilità elevata, la configurazione dell'host Docker e altro ancora. Un agente di orchestrazione è responsabile dell'esecuzione, della distribuzione, del ridimensionamento e della correzione dei carichi di lavoro in una raccolta di nodi. In genere, i prodotti per l'agente di orchestrazione sono gli stessi che forniscono l'infrastruttura cluster, ad esempio Mesosphere DC/OS, Kubernetes, Docker Swarm e Azure Service Fabric.


>[!div class="step-by-step"]
[Precedente](what-is-docker.md)
[Successivo](docker-containers-images-and-registries.md)
