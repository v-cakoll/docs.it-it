---
title: Introduzione a .NET e Docker
description: Informazioni sui Docker e .NET Core
keywords: .NET, .NET Core, Docker
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 03c28597-7e73-46d6-a9c3-f9cb55642739
manager: wpickett
ms.custom: mvc
ms.openlocfilehash: 1c9ce7a008c86d1c245ce8b7d616e05fcb3d4bbc
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="introduction-to-net-and-docker"></a>Introduzione a .NET e Docker

 Questo articolo fornisce un'introduzione e concetti di base per l'utilizzo di .NET su Docker. 

## <a name="docker-packaging-your-apps-to-deploy-and-run-anywhere"></a>Docker: Creazione di pacchetti per distribuire ed eseguire qualsiasi App

[Docker](https://docs.microsoft.com/dotnet/standard/microservices-architecture/container-docker-introduction/docker-defined) è una piattaforma aperta che consente agli sviluppatori e amministratori di compilare [immagini](https://docs.docker.com/glossary/?term=image), spedizione e l'esecuzione di applicazioni distribuite in un ambiente isolato a regime di controllo libero chiamato un [contenitore](https://www.docker.com/what-container). Questo approccio consente la gestione del ciclo di vita di un'applicazione efficiente tra ambienti di sviluppo, QA e produzione.
 
Il [piattaforma Docker](https://docs.docker.com/engine/docker-overview/#the-docker-platform) utilizza il [motore Docker](https://docs.docker.com/engine/docker-overview/#docker-engine) per compilare rapidamente e pacchetti di applicazioni di esempio [immagini Docker](https://docs.docker.com/glossary/?term=image) creato utilizzando i file scritti nel [Dockerfile ](https://docs.docker.com/glossary/?term=Dockerfile) formato che quindi viene distribuito ed eseguito un [a più livelli contenitore](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).

È possibile creare la propria [immagini sovrapposte](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers) come dockerfile o utilizzare quelli da esistenti un [Registro di sistema](https://docs.docker.com/glossary/?term=registry), ad esempio [Hub Docker](https://docs.docker.com/glossary/?term=Docker%20Hub).

Il [relazione tra i contenitori di Docker, immagini e i registri](https://docs.microsoft.com/dotnet/standard/microservices-architecture/container-docker-introduction/docker-containers-images-registries) è un concetto importante quando [architettura e la Creazione contenitore applicazioni o microservizi](https://docs.microsoft.com/dotnet/standard/microservices-architecture/architect-microservice-container-applications/). Questo approccio riduce notevolmente il tempo tra lo sviluppo e distribuzione.

### <a name="further-reading-and-watching"></a>Approfondimento (e guardare il video)

* [Contenitori basati su Windows: sviluppo di applicazioni moderne con controllo di livello aziendale.](https://www.youtube.com/watch?v=Ryx3o0rD5lY&feature=youtu.be)
* [Panoramica di docker](https://docs.docker.com/engine/docker-overview/)
* [Dockerfile in contenitori di Windows](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [Procedure consigliate per la scrittura di Dockerfile](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/)
* [Creazione di immagini Docker per le applicazioni .NET Core](../docker/building-net-docker-images.md)


### <a name="getting-net-docker-images"></a>Acquisizione delle immagini Docker .NET

Le immagini Docker .NET ufficiale vengono create e ottimizzate da Microsoft. Sono disponibili pubblicamente in repository Microsoft nell'Hub Docker. Ogni archivio può contenere più immagini, a seconda delle versioni di .NET e nelle versioni del sistema operativo. La maggior parte dei repository di immagini forniscono tag esteso per consentire la selezione sia una versione di framework specifico che un sistema operativo (versione di Windows o Linux distro).

## <a name="scenario-based-guidance"></a>Scenario basato su materiale sussidiario

Scopo di Microsoft per i repository .NET è hanno repository granulare e sono specifici, che rappresentano uno scenario specifico o un carico di lavoro.

Il `microsoft/aspnetcore` immagini sono ottimizzate per le applicazioni ASP.NET Core in Docker, in modo da contenitori possono avviare più velocemente.

Le immagini di .NET Core (`microsoft/dotnet`) sono progettate per applicazioni di console basate su .NET Core. Ad esempio, i processi batch, i processi Web di Azure e altri scenari di console devono utilizzare immagini .NET Core ottimizzate.

Lo scenario più evidente orizzontale per l'utilizzo di applicazioni .NET e Docker è per la distribuzione di produzione e di hosting. Si scopre che produzione sia un solo scenario altri quelli sono ugualmente utili. Questi scenari non sono specifici di .NET, ma dovrà essere applicata la maggior parte delle piattaforme di sviluppo.

* **Installare le forze di attrito bassa** , è possibile provare .NET senza un'installazione locale. Scaricare solo un'immagine di Docker con .NET in essa contenuti.

* **Sviluppare in un contenitore** , è possibile sviluppare in un ambiente coerenza, rendendo gli ambienti di sviluppo e produzione simile (come evitare problemi di stato globale nel computer di sviluppo). Visual Studio Tools per Docker consentono anche di avviare un contenitore direttamente da Visual Studio.

* **In un contenitore di test** , in un contenitore, è possibile testare riduzione degli errori a causa di ambienti non configurati correttamente o altre modifiche lasciati dall'ultimo test.

* **Compilazione in un contenitore** , è possibile compilare codice in un contenitore, evitando la necessità di configurare correttamente il computer di compilazione condivisa per più ambienti, ma invece spostare un "BYOC" (un contenitore di portare) approccio.

* **Distribuzione in tutti gli ambienti** , è possibile distribuire un'immagine con tutti gli ambienti. Questo approccio consente di ridurre gli errori a causa delle differenze di configurazione, in genere modifica il comportamento dell'immagine tramite configurazione esterni (ad esempio, le variabili di ambiente inserita).

[Linee guida generali](https://docs.microsoft.com/dotnet/standard/microservices-architecture/net-core-net-framework-containers/general-guidance) per decidere tra .NET Core e .NET Framework per lo sviluppo di contenitore Docker.

### <a name="common-docker-development-scenarios"></a>Scenari comuni di sviluppo di Docker

#### <a name="net-core"></a>.NET Core

**Risorse di .NET core**

 Selezionare gli esempi di .NET Core adattare gli scenari di interesse. Tutte le istruzioni di esempio illustrano come immagini di Windows o Linux Docker da Windows, Linux o macOS host di destinazione.

Gli esempi utilizzano .NET Core 2.0. Usano Docker [compilazione in più fasi](https://github.com/dotnet/announcements/issues/18) e [arch più tag](https://github.com/dotnet/announcements/issues/14) ove appropriato.

* [Immagini di .NET core su DockerHub](https://hub.docker.com/r/microsoft/dotnet/)

* [Dockerize un'applicazione .NET Core](https://docs.docker.com/engine/examples/dotnetcore/)

* Questo esempio di .NET Core Docker viene illustrato come [usare Docker nel processo di sviluppo .NET Core](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-dev). L'esempio funziona con contenitori di Linux e Windows.

* Questo esempio di .NET Core Docker viene illustrato un modello prassi migliori per [la creazione di immagini Docker per le applicazioni .NET Core per la produzione.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod) L'esempio funziona con contenitori di Linux e Windows.

* Questo [esempio .NET Core Docker](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-selfcontained) viene illustrato un modello migliore di procedure consigliate per la creazione di immagini Docker per [indipendente applicazioni .NET Core](https://docs.microsoft.com/dotnet/core/deploying/). Utilizzato per il contenitore più piccolo di produzione senza un vantaggio dal [la condivisione delle immagini di base tra i contenitori](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/). Tuttavia, potrebbero essere condivisa livelli inferiori di Docker.

#### <a name="arm32--raspberry-pi"></a>ARM32 / Raspberry Pi

* [Annuncio di .NET core Runtime ARM32 compilazioni](https://github.com/dotnet/announcements/issues/29)

* [ARM32 / Raspberry Pi .NET Core immagini in cui DockerHub](https://hub.docker.com/r/microsoft/dotnet/)

* [ARM32 / Pi al lampone .NET Core Docker esempi su GitHub](https://github.com/dotnet/dotnet-docker-samples#arm32--raspberry-pi)

#### <a name="net-framework"></a>.NET Framework

* [Le immagini di .NET framework in cui DockerHub](https://hub.docker.com/r/microsoft/dotnet-framework/) repository sono contenuti esempi che illustrano diverse configurazioni di .NET Framework Docker. È possibile usare queste immagini come base per le proprie immagini Docker.

**4.7 di .NET framework**

[Il [dotnet-esempio: 4.7 framework](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.7) viene illustrato l'utilizzo di "hello world" base del [.NET Framework 4.7](https://docs.microsoft.com/dotnet/framework/whats-new/index#introducing-the-net-framework-47). Illustra come è possibile compilare e distribuire l'app basarsi sul [immagine docker di .NET Framework 4.7](https://github.com/Microsoft/dotnet-framework-docker/blob/master/4.7/Dockerfile).

**.NET framework 4.6.2**

Il [dotnet-esempio: 4.6.2 framework](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.6.2) viene illustrato l'utilizzo di "hello world" base del [.NET Framework 4.6.2](https://docs.microsoft.com/dotnet/framework/whats-new/index#whats-new-in-the-net-framework-462). Illustra come è possibile compilare e distribuire l'app basarsi sul [immagine docker di .NET Framework 4.6.2](https://github.com/Microsoft/dotnet-framework-docker/tree/master/4.6.2).

**.NET framework 3.5**

 Il [dotnet-framework 3.5: esempio](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-3.5) viene illustrato l'utilizzo di "hello world" base di [.NET Framework 3.5](https://github.com/Microsoft/dotnet-framework-docker/tree/master/3.5). Illustra come compilare e distribuire un progetto di basarsi su .NET Framework 3.5 in Docker.

#### <a name="aspnet-core"></a>ASP.NET Core

* [In questo esempio di ASP.NET Core Docker](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) viene illustrato un modello migliore di procedure consigliate per la creazione di immagini Docker per ASP.NET Core App per la produzione. L'esempio funziona con contenitori di Linux e Windows.

* [Immagini ASP.NET Core DockerHub](https://hub.docker.com/r/microsoft/aspnetcore-build/)

* [Immagini di ASP.NET Core su GitHub](https://github.com/aspnet/aspnet-docker)

#### <a name="aspnet-framework"></a>Framework di ASP.NET 

* [Immagini di Framework di ASP.NET in cui DockerHub](https://hub.docker.com/r/microsoft/aspnet/)

* [App di Web Form ASP.NET in esempio di .NET Framework 4.6.2](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/aspnetapp)

#### <a name="windows-communication-framework-wcf"></a>Windows Communication Framework (WCF)

* [Immagini di Windows Communication Framework (WCF) in cui DockerHub](https://hub.docker.com/r/microsoft/wcf/)

* [Immagini di Windows Communication Framework (WCF) su GitHub](https://github.com/microsoft/iis-docker)

* [Esempi di Docker di Windows Communication Framework (WCF) utilizzando completa di .NET Framework 4.6.2](https://github.com/Microsoft/wcf-docker-samples)

#### <a name="internet-information-server-iis"></a>Internet Information Server (IIS)

* [Immagini di Internet Information Server (IIS) in cui DockerHub](https://hub.docker.com/r/microsoft/iis/)

* [Immagini di Internet Information Server (IIS) su GitHub](https://github.com/microsoft/wcf-docker)

### <a name="interact-with-other-microsoft-stack-container-images"></a>Interagire con altre immagini contenitore stack di Microsoft

#### <a name="microsoft-sql-server"></a>Microsoft SQL Server

* [Eseguire Microsoft SQL Server per l'immagine contenitore 2017 Linux con avvio rapido di Docker](https://docs.microsoft.com/sql/linux/quickstart-install-connect-docker)

* [Microsoft SQL Server per le immagini Linux in cui DockerHub](https://hub.docker.com/r/microsoft/mssql-server-windows/)

* [Immagini di Microsoft SQL Server per i contenitori di Windows in cui DockerHub](https://hub.docker.com/r/microsoft/mssql-server-windows/)

* [Immagini di Microsoft SQL Server Express Edition per i contenitori di Windows in cui DockerHub](https://hub.docker.com/r/microsoft/mssql-server-windows-express/)

* [Immagini di Microsoft SQL Server Developer Edition per i contenitori di Windows in cui DockerHub](https://hub.docker.com/r/microsoft/mssql-server-windows-developer/)

#### <a name="visual-studio-team-services-vsts-agent"></a>Agente di Visual Studio Team Services (VSTS)

* [Visual Studio Team Services (VSTS) agente immagini create DockerHub](https://hub.docker.com/r/microsoft/vsts-agent/)

* [Visual Studio Team Services (VSTS) agente le immagini su GitHub](https://github.com/Microsoft/vsts-agent-docker)

#### <a name="operations-management-suite-oms-linux-agent"></a>Agente di Operations Management Suite (OMS) Linux

* [Panoramica dell'agente di Operations Management Suite (OMS) Linux](https://github.com/Microsoft/OMS-Agent-for-Linux/blob/master/docs/Docker-Instructions.md#overview)

* [Immagini di Operations Management Suite (OMS) in cui DockerHub](https://hub.docker.com/r/microsoft/vsts-agent/) 

* [Immagini di Operations Management Suite (OMS) su GitHub](https://github.com/Microsoft/OMS-docker)

#### <a name="microsoft-azure-command-line-interface-cli"></a>Interfaccia della riga di comando (CLI) Microsoft Azure

* [Immagini di interfaccia della riga di comando (CLI) di Microsoft Azure in cui DockerHub](Docker image for Microsoft Azure Command Line Interface) 

* [Immagini di Microsoft Azure interfaccia della riga di comando (CLI) su GitHub](https://github.com/Microsoft/OMS-docker)

> [!Note]
> Se non si dispone di una sottoscrizione di Azure, [Iscriviti oggi stesso](https://azure.microsoft.com/free/?b=16.48) per un account gratuito di 30 giorni e get 200 dollari di crediti di Azure per provare qualsiasi combinazione di servizi di Azure.
>

#### <a name="microsoft-azure-cosmos-db-emulator-windows-containers-only"></a>Emulatore Cosmos DB di Microsoft Azure (solo per i contenitori di Windows)

* [Immagini di emulatore di Microsoft Azure Cosmos DB in cui DockerHub](https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator) 

* [Usare l'emulatore di DB Cosmos di Azure per sviluppo locale e il test](https://docs.microsoft.com/azure/cosmos-db/local-emulator#developing-with-the-emulator)

## <a name="exploring-the-rich-docker-development-ecosystem"></a>Esplorazione dell'ecosistema di sviluppo avanzato Docker

Ora che si è appreso sulla piattaforma Docker e immagini Docker diverse, il passaggio successivo consiste nell'esplorazione nell'ecosistema Docker RTF. I collegamenti seguenti viene illustrato come gli strumenti Microsoft complemento sviluppo contenitore.

* [Utilizzo combinato di .NET e Docker](https://blogs.msdn.microsoft.com/dotnet/2017/05/25/using-net-and-docker-together/) 
* [Progettazione e sviluppo di applicazioni multi-contenitore e Microservizio basato su .NET](../standard/microservices-architecture/multi-container-microservice-net-applications)
* [Estensione di Visual Studio codice Docker](https://code.visualstudio.com/docs/languages/dockerfile) 
* [Imparare a usare Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/) 
* [Esempio introduttivo di recupero di Service Fabric](https://azure.microsoft.com/resources/samples/service-fabric-dotnet-getting-started/)
* [Vantaggi dei contenitori di Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/index#video-overview)
* [Utilizzo degli strumenti di Visual Studio Docker](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [Distribuzione di immagini Docker dal Registro di sistema contenitore di Azure per le istanze di contenitore di Azure](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* [Il debug con codice di Visual Studio](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* [Recupero mani nel con Visual Studio per Mac, contenitori e senza codice nel cloud](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [Introduzione a Docker e Visual Studio per Mac Lab](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)

## <a name="next-steps"></a>Passaggi successivi

* [Nozioni di Docker con .NET Core](../docker/docker-basics-dotnet-core.md)
* [Creazione di immagini Docker di .NET Core](../docker/building-net-docker-images)