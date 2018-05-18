---
title: Terminologia di Docker
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Terminologia di Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 9bbeff8c467e762e682fdaf99c8a11851b291db8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="docker-terminology"></a>Terminologia di Docker

Questa sezione elenca i termini e le definizioni che è necessario conoscere prima di approfondire ulteriormente Docker. Per altre definizioni, vedere il [glossario](https://docs.docker.com/glossary/) completo fornito da Docker.

**Immagine del contenitore**: pacchetto con tutte le dipendenze e le informazioni necessarie per creare un contenitore. Un'immagine include tutte le dipendenze, ad esempio i framework, oltre alla configurazione della distribuzione e dell'esecuzione che deve essere usata dal runtime del contenitore. In genere, un'immagine deriva da più immagini di base con livelli impilati uno sopra l'altro in modo da formare il file system del contenitore. Un'immagine non può essere modificata dopo che è stata creata.

**Contenitore**: istanza di un'immagine Docker. Un contenitore rappresenta l'esecuzione di una singola applicazione o di un singolo processo o servizio. È costituito dal contenuto di un'immagine Docker, da un ambiente di esecuzione e da un set di istruzioni standard. Quando si ridimensiona un servizio, si creano più istanze di un contenitore dalla stessa immagine oppure in un processo batch può creare più contenitori dalla stessa immagine, passando parametri diversi a ogni istanza.

**Tag**: contrassegno o etichetta che si può applicare alle immagini per poter identificare immagini o versioni diverse della stessa immagine, a seconda del numero di versione o dell'ambiente di destinazione.

**Dockerfile**: file di testo contenente le istruzioni per compilare un'immagine Docker.

**Compilazione**: azione di compilazione di un'immagine del contenitore in base alle informazioni e al contesto forniti dal Dockerfile corrispondente e ad altri file aggiuntivi nella cartella in cui viene creata l'immagine. È possibile compilare immagini con il comando Docker docker build.

**Repository**: raccolta di immagini Docker correlate, etichettate con un tag che indica la versione dell'immagine. Alcuni repository contengono più varianti di un'immagine specifica, ad esempio un'immagine contenente gli SDK (più pesante), un'immagine contenente solo i runtime (più leggera) e così via. Tali varianti possono essere contrassegnate con i tag. Un singolo repository può contenere varianti di piattaforme, ad esempio un'immagine Linux e un'immagine Windows.

**Registro**: servizio che fornisce l'accesso ai repository. Il registro predefinito per la maggior parte delle immagini pubbliche è l'[Hub Docker](https://hub.docker.com/), di proprietà di Docker a livello di organizzazione. Un registro contiene in genere i repository di più team. Spesso le aziende hanno registri privati in cui archiviare e gestire le immagini che hanno creato. Registro contenitori di Azure è un esempio.

**Hub Docker**: registro pubblico in cui caricare le immagini e usarle. L'hub Docker fornisce l'hosting di immagini Docker, registri pubblici o privati, trigger e webhook di compilazione e integrazione con GitHub e Bitbucket.

**Registro contenitori di Azure**: risorsa pubblica per l'uso di immagini Docker e dei relativi componenti in Azure. Fornisce un registro vicino alle distribuzioni in Azure e offre il controllo sugli accessi, tramite i gruppi e le autorizzazioni di Azure Active Directory.

**Docker Trusted Registry (DTR)**: servizio di registro Docker (di Docker) che può essere installato in locale per risiedere all'interno del data center e della rete dell'organizzazione. È una soluzione pratica per le immagini private che devono essere gestite all'interno dell'azienda. Docker Trusted Registry è incluso nel prodotto Docker Datacenter. Per altre informazioni, vedere [Docker Trusted Registry (DTR)](https://docs.docker.com/docker-trusted-registry/overview/).

**Docker Community Edition (CE)**: strumenti di sviluppo per Windows e macOS per la compilazione, l'esecuzione e il test dei contenitori in locale. Docker CE per Windows offre ambienti di sviluppo per contenitori Linux e Windows. L'host Docker Linux in Windows è basato su una macchina virtuale [Hyper-V](https://www.microsoft.com/en-us/server-cloud/solutions/virtualization.aspx). L'host per Contenitori Windows è direttamente basato su Windows. Docker CE per Mac è basato sul framework Hypervisor di Apple e sull'[hypervisor xhyve](https://github.com/mist64/xhyve), che fornisce una macchina virtuale host Docker Linux in Mac OS X. Docker CE per Windows e per Mac sostituisce Docker Toolbox, basato su Oracle VirtualBox.

**Docker Enterprise Edition (EE)**: versione di livello aziendale degli strumenti Docker per lo sviluppo per Linux e Windows.

**Compose**: strumento da riga di comando e formato di file YAML con i metadati per definire ed eseguire applicazioni multicontenitore. Si definisce una singola applicazione in base a più immagini con uno o più file YML che possono eseguire l'override dei valori a seconda dell'ambiente. Dopo aver creato le definizioni, è possibile distribuire l'intera applicazione multicontenitore con un singolo comando (a partire da docker-compose) che crea un contenitore per immagine nell'host Docker.

**Cluster**: raccolta di host Docker esposta come se si trattasse di un singolo host Docker virtuale, per consentire la scalabilità aggiungendo più istanze dei servizi distribuite tra più host all'interno del cluster. È possibile creare i cluster Docker con Docker Swarm, Mesosphere DC/OS, Kubernetes e Azure Service Fabric. Se si usa Docker Swarm per gestire un cluster, si farà normalmente riferimento al cluster chiamandolo *swarm* anziché cluster.

**Agente di orchestrazione**: strumento che semplifica la gestione di cluster e host Docker. Gli agenti di orchestrazione consentono di gestire immagini, contenitori e host tramite un'interfaccia della riga di comando o un'interfaccia utente grafica. È possibile gestire le reti di contenitori, le configurazioni, il bilanciamento del carico, l'individuazione di servizi, la disponibilità elevata, la configurazione dell'host Docker e altro ancora. Un agente di orchestrazione è responsabile dell'esecuzione, della distribuzione, del ridimensionamento e della correzione dei carichi di lavoro in una raccolta di nodi. In genere, i prodotti per l'agente di orchestrazione sono gli stessi che forniscono l'infrastruttura cluster, ad esempio Mesosphere DC/OS, Kubernetes, Docker Swarm e Azure Service Fabric.


>[!div class="step-by-step"]
[Indietro] (docker-defined.md) [Avanti] (docker-containers-images-registries.md)
