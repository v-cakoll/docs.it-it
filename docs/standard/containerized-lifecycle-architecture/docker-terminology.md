---
title: Terminologia di Docker
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 853474a18e5c7253b88db7fb651ee447242bb9f2
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2018
---
# <a name="docker-terminology"></a>Terminologia di Docker

Questa sezione sono elencati i termini e definizioni con cui è necessario acquisire familiarità prima di analizzare più approfondita Docker (per un'ulteriore definizioni, vedere esteso [glossario](https://docs.docker.com/glossary/) fornito da Docker in <https://docs.docker.com/glossary/>:

-   **Immagine contenitore** un pacchetto con tutte le dipendenze e le informazioni necessarie per creare un contenitore. Un'immagine include tutte le dipendenze (ad esempio Framework) e distribuzione e configurazione utilizzabile da un runtime del contenitore. In genere, un'immagine deriva da più immagini di base che sono livelli disposte in pila una sopra l'altro per formare il sistema di file del contenitore. Un'immagine non è modificabile dopo che è stato creato.

-   **Contenitore** un'istanza di un'immagine di Docker. Un contenitore rappresenta un runtime per una singola applicazione, un processo o un servizio. È costituito il contenuto di un'immagine di Docker, un ambiente di runtime e un set standard di istruzioni. Quando si ridimensiona un servizio, si creano più istanze di un contenitore dalla stessa immagine oppure In alternativa, un processo batch è possibile creare più contenitori dalla stessa immagine, il passaggio di parametri diversi per ogni istanza.

-   **Tag** un contrassegno o un'etichetta che è possibile applicare alle immagini in modo che possono essere identificate immagini differenti o le versioni della stessa immagine (a seconda il numero di versione o l'ambiente di destinazione).

-   **Dockerfile** un file di testo contenente istruzioni su come creare un'immagine di Docker.

-   **Compilare** l'azione di compilazione di un'immagine contenitore in base alle informazioni e contesto fornito dal relativo Dockerfile e i file aggiuntivi nella cartella in cui l'immagine viene creata. È possibile creare immagini usando il comando di compilazione docker Docker.

-   **Repository (noto anche come repository)** una raccolta di immagini Docker correlate con etichettata con un tag che indica la versione dell'immagine. Alcuni archivi contengono più varianti di un'immagine specifica, ad esempio un'immagine contenente SDK (peso), un'immagine che contiene solo i Runtime (più chiari), e così via. Tali varianti possono essere contrassegnate con i tag. Un unico archivio può contenere le varianti della piattaforma, ad esempio un'immagine Linux e un'immagine di Windows.

-   **Registro di sistema** un servizio che fornisce l'accesso al repository. Il registro predefinito per la maggior parte delle immagini pubbliche è l'[Hub Docker](https://hub.docker.com/), di proprietà di Docker a livello di organizzazione. Un registro contiene in genere i repository di più team. Le società hanno spesso registri privati per archiviare e gestire le immagini create. *Registro di sistema Azure contenitore* è un altro esempio.

-   **Hub docker** un registro di sistema pubblico per il caricamento di immagini e utilizzarli. L'hub Docker fornisce l'hosting di immagini Docker, registri pubblici o privati, trigger e webhook di compilazione e integrazione con GitHub e Bitbucket.

-   **Registro di sistema Azure contenitore** una risorsa pubblica per l'utilizzo di immagini Docker e i relativi componenti in Azure. Fornisce un registro vicino alle distribuzioni in Azure e offre il controllo sugli accessi, tramite i gruppi e le autorizzazioni di Azure Active Directory.

-   **Docker Trusted del Registro di sistema DTR** servizio Registro di sistema A Docker (da Docker) che è possibile installare in locale in modo che si trova all'interno di Data Center e alla rete dell'organizzazione. È una soluzione pratica per le immagini private che devono essere gestite all'interno dell'azienda. Docker Trusted Registry è incluso nel prodotto Docker Datacenter. Per altre informazioni, visitare [ https://docs.docker.com/docker-trusted-registry/overview/ ](https://docs.docker.com/docker-trusted-registry/overview/).

-   **Docker Community Edition (CE)** strumenti di sviluppo per Windows e macOS per la compilazione, in esecuzione e test di contenitori in locale. Docker CE per Windows offre ambienti di sviluppo per contenitori Linux e Windows. L'host Linux Docker in Windows si basa su un [Hyper-V](https://www.microsoft.com/en-us/server-cloud/solutions/virtualization.aspx) macchina virtuale. L'host per Contenitori Windows è direttamente basato su Windows. Docker CE per Mac si basa su framework Apple Hypervisor e [xhyve hypervisor](https://github.com/mist64/xhyve), che fornisce un host Linux Docker VM in Mac OS x Docker CE per Windows e per Mac sostituisce della casella degli strumenti di Docker, che è basato su Oracle VirtualBox.

-   **Docker Enterprise Edition (EE)** una versione su larga scala degli strumenti di Docker per lo sviluppo di Linux e Windows.

-   **Comporre** un strumento da riga di comando e YAML formato con i metadati per la definizione e l'esecuzione di applicazioni multicontainer di file. Si definisce una singola applicazione in base a più immagini con uno o più file YML che possono eseguire l'override dei valori a seconda dell'ambiente. Dopo aver creato le definizioni, è possibile distribuire l'intera applicazione multicontainer utilizzando un unico comando (docker-comporre backup) che crea un contenitore per ogni immagine dell'host Docker.

-   **Cluster** un insieme di host Docker esposto come se fossero un unico host Docker virtuale in modo che l'applicazione è possibile scalare a più istanze dei servizi distribuiti tra più host all'interno del cluster. È possibile creare cluster di Docker tramite Docker Swarm Mesosphere DC/OS, Kubernetes e Azure Service Fabric. Se si usa Docker Swarm per gestire un cluster, si farà normalmente riferimento al cluster chiamandolo *swarm* anziché cluster.

-   **Orchestrator** uno strumento che semplifica la gestione di host Docker e cluster. Utilizza orchestrators, è possibile gestire le immagini, contenitori e gli host tramite CLI o un'interfaccia utente grafica. È possibile gestire le reti di contenitori, le configurazioni, il bilanciamento del carico, l'individuazione di servizi, la disponibilità elevata, la configurazione dell'host Docker e altro ancora. Un agente di orchestrazione è responsabile dell'esecuzione, della distribuzione, del ridimensionamento e della correzione dei carichi di lavoro in una raccolta di nodi. In genere, i prodotti per l'agente di orchestrazione sono gli stessi che forniscono l'infrastruttura cluster, ad esempio Mesosphere DC/OS, Kubernetes, Docker Swarm e Azure Service Fabric.


>[!div class="step-by-step"]
[Precedente] (analisi-è-docker.md) [Avanti] (docker-contenitori-immagini-e-registries.md)
