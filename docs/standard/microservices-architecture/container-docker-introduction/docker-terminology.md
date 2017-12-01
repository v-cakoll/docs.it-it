---
title: Terminologia di docker
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Terminologia di docker
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 885b1fbd3369dec54ebde21a5378630c764f852d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="docker-terminology"></a>Terminologia di docker

Questa sezione elenca i termini e definizioni, che è necessario conoscere prima di ottenere più approfondito in Docker. Per ulteriori definizioni, vedere esteso [glossario](https://docs.docker.com/v1.11/engine/reference/glossary/) fornito da Docker.

**Immagine contenitore**: un pacchetto con tutte le dipendenze e le informazioni necessarie per creare un contenitore. Un'immagine include tutte le dipendenze (ad esempio Framework) e configurazione di distribuzione ed esecuzione utilizzabile da un runtime del contenitore. In genere, un'immagine deriva da più immagini di base che sono i livelli in pila sopra l'altro per formare filesystem del contenitore. Un'immagine non è modificabile dopo che è stato creato.

**Contenitore**: un'istanza di un'immagine di Docker. Un contenitore rappresenta l'esecuzione di una singola applicazione, un processo o un servizio. È costituito il contenuto di un'immagine di Docker, un ambiente di esecuzione e un set standard di istruzioni. Quando si ridimensiona un servizio, è creare più istanze di un contenitore dalla stessa immagine. In un processo batch è possibile creare più contenitori dalla stessa immagine, il passaggio di parametri diversi per ogni istanza.

**Tag**: un contrassegno o un'etichetta, è possibile applicare alle immagini in modo che possono essere identificate immagini differenti o le versioni della stessa immagine (a seconda il numero di versione o l'ambiente di destinazione).

**Dockerfile**: un file di testo contenente istruzioni su come creare un'immagine di Docker.

**Compilare**: l'azione di compilazione di un'immagine contenitore in base alle informazioni e contesto fornito dal relativo Dockerfile e file aggiuntivi nella cartella in cui l'immagine viene creata. È possibile creare immagini con il comando di compilazione docker Docker.

**Repository (repository)**: una raccolta di immagini Docker correlate, con l'etichetta con un tag che indica la versione dell'immagine. Alcuni repository contiene più varianti di un'immagine specifica, ad esempio un'immagine contenente SDK (peso), un'immagine che contiene solo i Runtime (più chiari) e così via. Queste varianti possono essere contrassegnate con tag. Un singolo repository può contenere le varianti della piattaforma, ad esempio un'immagine Linux e un'immagine di Windows.

**Registro di sistema**: un servizio che fornisce l'accesso al repository. Il Registro di sistema predefinito per le immagini più pubbliche [Hub Docker](https://hub.docker.com/) (proprietà di Docker come un'organizzazione). Un registro di sistema contiene in genere repository da più team. Le società hanno spesso registri privati per archiviare e gestire le immagini create. Registro di sistema di contenitore di Azure è un altro esempio.

**Hub docker**: un registro di sistema pubblico per il caricamento di immagini e utilizzarli. Hub docker fornisce Docker immagine hosting, registri di sistema pubblici o privati, i trigger di compilazione e hook web e integrazione con GitHub e Bitbucket.

**Registro di sistema Azure contenitore**: una risorsa pubblica per l'utilizzo di immagini Docker e i relativi componenti in Azure. Fornisce un registro di sistema che è vicino alle distribuzioni in Azure e che consente di controllare l'accesso, che consente di utilizzare i gruppi di Azure Active Directory e le autorizzazioni.

**Docker Trusted del Registro di sistema DTR**: servizio Registro di sistema A Docker (da Docker) che può essere installata in locale, pertanto si trova all'interno di Data Center e alla rete dell'organizzazione. È utile per le immagini private che devono essere gestite all'interno dell'organizzazione. Registro attendibile docker è incluso come parte del prodotto Data Center di Docker. Per ulteriori informazioni, vedere [Docker Trusted del Registro di sistema DTR](https://docs.docker.com/docker-trusted-registry/overview/).

**Docker Community Edition (CE)**: strumenti di sviluppo per Windows e macOS per la compilazione, in esecuzione e test di contenitori in locale. CE docker per Windows fornisce gli ambienti di sviluppo per i contenitori di Windows e Linux. L'host Linux Docker in Windows si basa su un [Hyper-V](https://www.microsoft.com/en-us/server-cloud/solutions/virtualization.aspx) macchina virtuale. L'host per i contenitori di Windows si basa direttamente su Windows. Docker CE per Mac si basa su framework Apple Hypervisor e [xhyve hypervisor](https://github.com/mist64/xhyve), che fornisce una macchina virtuale dell'host Linux Docker in Mac OS x Docker CE per Windows e per Mac sostituisce della casella degli strumenti di Docker, che è basato su Oracle VirtualBox.

**Docker Enterprise Edition (EE)**: una versione su larga scala degli strumenti di Docker per lo sviluppo di Linux e Windows.

**Comporre**: un strumento da riga di comando e YAML formato con i metadati per la definizione e l'esecuzione di applicazioni multi-contenitore di file. È possibile definire una singola applicazione basata su più immagini con uno o più file .yml che è possono eseguire l'override di valori a seconda dell'ambiente. Dopo aver creato le definizioni, è possibile distribuire l'applicazione completamente multi-contenitore con un unico comando (docker-comporre backup) che crea un contenitore per ogni immagine dell'host Docker.

**Cluster**: una raccolta di host Docker esposto come se fosse un singolo host Docker virtuale, in modo che l'applicazione è possibile scalare a più istanze dei servizi distribuiti tra più host all'interno del cluster. È possibile creare cluster di docker con Docker Swarm Mesosphere DC/OS, Kubernetes e Azure Service Fabric. (Se si usa Docker Swarm per la gestione di un cluster, in genere fare riferimento al cluster come un *swarm* invece di un cluster.)

**Orchestrator**: uno strumento che semplifica la gestione di host Docker e cluster. Orchestrators consentono di gestire le immagini, contenitori e gli host tramite un'interfaccia della riga di comando (CLI) o un'interfaccia utente grafica. È possibile gestire una rete di contenitori, configurazioni, il bilanciamento del carico, l'individuazione del servizio, la disponibilità elevata, configurazione dell'host Docker e più. Agente di orchestrazione è responsabile per l'esecuzione, la distribuzione, scalabilità e la correzione dei carichi di lavoro in una raccolta di nodi. In genere, i prodotti di orchestrator sono gli stessi prodotti che forniscono l'infrastruttura di cluster, ad esempio Mesosphere DC/OS, Kubernetes, Docker Swarm e Azure Service Fabric.


>[!div class="step-by-step"]
[Precedente] (docker-defined.md) [Avanti] (docker contenitori-immagini registries.md)
