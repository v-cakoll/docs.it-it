---
title: Introduzione a Docker - .NET Core
description: Questo articolo fornisce un'introduzione e una panoramica di Docker nel contesto di un'applicazione .NET Core.
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.custom: mvc, seodec18
ms.openlocfilehash: 1655d4652c4e9b48c48a2a22c2a1bf6cdd459088
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148886"
---
# <a name="introduction-to-net-and-docker"></a>Introduzione a .NET e Docker

Questo articolo fornisce un'introduzione e i concetti di base per usare .NET in Docker.

## <a name="docker-packaging-your-apps-to-deploy-and-run-anywhere"></a>Docker: creazione di pacchetti delle app per distribuirle ed eseguirle ovunque

[Docker](../../standard/microservices-architecture/container-docker-introduction/docker-defined.md) è una piattaforma aperta che consente agli sviluppatori e agli amministratori di compilare [immagini](https://docs.docker.com/glossary/?term=image) e di inviare ed eseguire le applicazioni distribuite in un ambiente scarsamente isolato denominato [contenitore](https://www.docker.com/what-container). Questo approccio consente una gestione efficiente del ciclo di vita delle applicazioni in ambienti di sviluppo, controllo di qualità e produzione.
 
La [piattaforma Docker](https://docs.docker.com/engine/docker-overview/#the-docker-platform) usa il [motore Docker](https://docs.docker.com/engine/docker-overview/#docker-engine) per compilare e creare rapidamente pacchetti di app come [immagini Docker](https://docs.docker.com/glossary/?term=image) create usando file scritti in formato [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) che viene quindi distribuito ed eseguito in un [contenitore su più livelli](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).

È possibile creare le proprie [immagini su più livelli](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers) come dockerfile o usare quelle esistenti di un [registro](https://docs.docker.com/glossary/?term=registry), ad esempio l'[hub Docker](https://docs.docker.com/glossary/?term=Docker%20Hub).

La [relazione tra contenitori, immagini e registri Docker](../../standard/microservices-architecture/container-docker-introduction/docker-containers-images-registries.md) è un concetto importante per l'[architettura e la compilazione di applicazioni o microservizi inclusi in contenitori](../../standard/microservices-architecture/architect-microservice-container-applications/index.md). Questo approccio riduce considerevolmente il tempo che intercorre tra lo sviluppo e la distribuzione.

### <a name="further-reading-and-watching"></a>Altre informazioni e video

* [Windows-based containers: Modern app development with enterprise-grade control](https://www.youtube.com/watch?v=Ryx3o0rD5lY&feature=youtu.be) (Contenitori basati su Windows: sviluppo di app moderne con controllo di livello aziendale)
* [Docker overview](https://docs.docker.com/engine/docker-overview/) (Panoramica di Docker)
* [Dockerfile on Windows Containers](/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile) (Dockerfile in contenitori Windows)
* [Best practices for writing Dockerfiles](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/) (Procedure consigliate per la scrittura di dockerfile)
* [Compilazione di immagini Docker per applicazioni .NET Core](../docker/building-net-docker-images.md)


### <a name="getting-net-docker-images"></a>Acquisizione di immagini Docker .NET

Le immagini Docker .NET ufficiali vengono create e ottimizzate da Microsoft. Sono disponibili pubblicamente nei repository Microsoft nell'hub Docker. Ogni repository può contenere più immagini, a seconda delle versioni di .NET e del sistema operativo. La maggior parte dei repository di immagini fornisce contrassegni completi che consentono di selezionare sia una versione specifica del framework che un sistema operativo (distribuzione di Linux o versione di Windows).

## <a name="scenario-based-guidance"></a>Linee guida basate sullo scenario

Lo scopo di Microsoft per i repository .NET è quello di avere repository granulari e mirati, che rappresentano uno specifico scenario o carico di lavoro.

Poiché le immagini `microsoft/aspnetcore` sono ottimizzate per le app ASP.NET Core in Docker, i contenitori possono essere avviati più rapidamente.

Le immagini .NET Core (`microsoft/dotnet`) sono destinate alle app console basate su .NET Core. I processi batch, Processi Web di Azure e altri scenari di console devono usare le immagini .NET Core ottimizzate.

Lo scenario orizzontale più ovvio per l'uso di applicazioni Docker e .NET è quello relativo alla distribuzione di produzione e all'hosting. La produzione dopotutto è solo uno scenario e anche gli altri sono ugualmente utili. Questi scenari non sono specifici di .NET, ma dovrebbero applicarsi alla maggior parte delle piattaforme di sviluppo.

* **Installazione a impatto ridotto**: è possibile provare .NET senza un'installazione locale. È sufficiente scaricare un'immagine Docker contenente .NET.

* **Eseguire lo sviluppo in un contenitore**: è possibile eseguire lo sviluppo in un ambiente coerente, rendendo simili gli ambienti di sviluppo e di produzione (evitando problemi come lo stato globale nei computer di sviluppo). Visual Studio Tools per Docker consente anche di avviare un contenitore direttamente da Visual Studio.

* **Eseguire il test in un contenitore**: è possibile eseguire il test in un contenitore, riducendo gli errori dovuti ad ambienti non correttamente configurati o ad altre modifiche ancora presenti dopo l'ultimo test.

* **Eseguire la compilazione in un contenitore**: è possibile compilare il codice in un contenitore, evitando di dover configurare correttamente computer di compilazione condivisi per più ambienti e passando invece a un approccio "BYOC" (Bring Your Own Container).

* **Distribuzione in tutti gli ambienti**: è possibile distribuire un'immagine in tutti gli ambienti. Questo approccio riduce gli errori dovuti alle differenze di configurazione, in genere modificando il comportamento dell'immagine tramite la configurazione esterna (ad esempio, variabili di ambiente inserite).

[Linee guida generali](../../standard/microservices-architecture/net-core-net-framework-containers/general-guidance.md) per scegliere tra .NET Core e .NET Framework per lo sviluppo di contenitori Docker.

### <a name="common-docker-development-scenarios"></a>Scenari comuni di sviluppo Docker

#### <a name="net-core"></a>.NET Core

**Risorse di .NET Core**

 Selezionare gli esempi di .NET Core adatti agli scenari a cui si è interessati. Tutte le istruzioni di esempio illustrano come specificare come destinazione immagini Docker Windows o Linux dagli host Windows, Linux o macOS.

Gli esempi usano .NET Core 2.0 e, dove appropriato, usano la [compilazione in più fasi](https://github.com/dotnet/announcements/issues/18) e i [tag per più architetture](https://github.com/dotnet/announcements/issues/14) di Docker.

* [.NET Core images on DockerHub](https://hub.docker.com/r/microsoft/dotnet/) (Immagini .NET Core in DockerHub)

* [Dockerize a .NET Core application](https://docs.docker.com/engine/examples/dotnetcore/) (Usare i contenitori Docker per un'applicazione .NET Core.)

* Questo esempio di Docker per .NET Core illustra come [usare Docker nel processo di sviluppo .NET Core](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-dev). L'esempio usa contenitori sia Linux che Windows.

* Questo esempio di Docker per .NET Core illustra un modello di procedura consigliata per la [compilazione di immagini Docker per app .NET Core per la produzione](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod). L'esempio usa contenitori sia Linux che Windows.

* Questo [esempio di Docker per .NET Core](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-selfcontained) illustra un modello di procedura consigliata per la compilazione di immagini Docker per [applicazioni .NET Core autonome](../deploying/index.md). Viene usato per il contenitore di produzione più piccolo senza i vantaggi della [condivisione delle immagini di base tra i contenitori](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/). È tuttavia possibile condividere livelli di Docker inferiori.

#### <a name="arm32--raspberry-pi"></a>ARM32/Raspberry Pi

* [.NET Core Runtime ARM32 builds announcement](https://github.com/dotnet/announcements/issues/29) (Annunci relativi alle build ARM32 del runtime di .NET Core)

* [ARM32 / Raspberry Pi .NET Core images on DockerHub](https://hub.docker.com/r/microsoft/dotnet/) (Immagini .NET Core per ARM32/Raspberry Pi in DockerHub)

* [ARM32 / Raspberry Pi .NET Core Docker Samples on GitHub](https://github.com/dotnet/dotnet-docker-samples#arm32--raspberry-pi) (Esempi di Docker per .NET Core ARM32/Raspberry Pi in GitHub)

#### <a name="net-framework"></a>.NET Framework

* [.NET Framework images on DockerHub](https://hub.docker.com/r/microsoft/dotnet-framework/) (Immagini .NET Framework in DockerHub)

Questo repository contiene esempi che illustrano diverse configurazioni Docker per .NET Framework. È possibile usare queste immagini come base per le proprie immagini Docker.

**.NET Framework 4.7**

L'[esempio dotnet-framework:4.7](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.7) illustra l'utilizzo di "hello world" di base di [.NET Framework 4.7](../../framework/whats-new/index.md#v47) e spiega come compilare e distribuire l'app basandosi sull'[immagine Docker per .NET Framework 4.7](https://github.com/Microsoft/dotnet-framework-docker-samples/blob/master/dotnetapp-4.7/Dockerfile).

**.NET Framework 4.6.2**

L'[esempio dotnet-framework:4.6.2](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.6.2) illustra l'utilizzo di "hello world" di base di [.NET Framework 4.6.2](../../framework/whats-new/index.md#v462) e spiega come compilare e distribuire l'app basandosi sull'[immagine Docker per .NET Framework 4.6.2](https://github.com/Microsoft/dotnet-framework-docker-samples/blob/master/dotnetapp-4.6.2/Dockerfile).

**.NET Framework 3.5**

 L'[esempio dotnet-framework:3.5](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-3.5) illustra l'utilizzo di "hello world" di base di [.NET Framework 3.5](https://github.com/Microsoft/dotnet-framework-docker-samples/blob/master/dotnetapp-3.5/dotnetapp-3.5/Dockerfile) e spiega come compilare e distribuire un progetto basandosi su .NET Framework 3.5 in Docker.

#### <a name="aspnet-core"></a>ASP.NET Core

* [Questo esempio di Docker per ASP.NET Core](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) illustra un modello di procedura consigliata per la compilazione di immagini Docker per app ASP.NET Core per la produzione. L'esempio usa contenitori sia Linux che Windows.

* [ASP.NET Core images on DockerHub](https://hub.docker.com/r/microsoft/aspnetcore-build/) (Immagini ASP.NET Core in DockerHub)

* [ASP.NET Core images on GitHub](https://github.com/aspnet/aspnet-docker) (Immagini ASP.NET Core in GitHub)

#### <a name="aspnet-framework"></a>Framework ASP.NET

* [ASP.NET Framework images on DockerHub](https://hub.docker.com/r/microsoft/aspnet/) (Immagini del framework ASP.NET in DockerHub)

* [ASP.NET Web Forms app on .NET Framework 4.6.2 sample](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/aspnetapp) (Esempio di app Web Forms ASP.NET in .NET Framework 4.6.2)

#### <a name="windows-communication-framework-wcf"></a>Windows Communication Framework (WCF)

* [Windows Communication Framework (WCF) images on DockerHub](https://hub.docker.com/r/microsoft/wcf/) (Immagini Windows Communication Framework (WCF) in DockerHub)

* [Windows Communication Framework (WCF) images on GitHub](https://github.com/microsoft/wcf-docker) (Immagini Windows Communication Framework (WCF) in GitHub)

* [Windows Communication Framework (WCF) Docker samples using .NET Framework 4.6.2](https://github.com/Microsoft/wcf-docker-samples) (Esempi di Docker per Windows Communication Framework (WCF) con .NET Framework 4.6.2)

#### <a name="internet-information-server-iis"></a>Internet Information Server (IIS)

* [Internet Information Server (IIS) images on DockerHub](https://hub.docker.com/r/microsoft/iis/) (Immagini Internet Information Server (IIS) in DockerHub)

* [Internet Information Server (IIS) images on GitHub](https://github.com/microsoft/iis-docker) (Immagini Internet Information Server (IIS) in GitHub)

### <a name="interact-with-other-microsoft-stack-container-images"></a>Interagire con altre immagini del contenitore di stack Microsoft

#### <a name="microsoft-sql-server"></a>Microsoft SQL Server

* [Guida introduttiva all'esecuzione dell'immagine del contenitore di Microsoft SQL Server per Linux 2017 con Docker](https://docs.microsoft.com/sql/linux/quickstart-install-connect-docker)

* [Microsoft SQL Server for Linux images on DockerHub](https://hub.docker.com/r/microsoft/mssql-server-linux/) (Immagini Microsoft SQL Server per Linux in DockerHub)

* [Microsoft SQL Server Express Edition images for Windows Containers on DockerHub](https://hub.docker.com/r/microsoft/mssql-server-windows-express/) (Immagini Microsoft SQL Server Express Edition per contenitori Windows in DockerHub)

* [Microsoft SQL Server Developer Edition images for Windows Containers on DockerHub](https://hub.docker.com/r/microsoft/mssql-server-windows-developer/) (Immagini Microsoft SQL Server Developer Edition per contenitori Windows in DockerHub)

#### <a name="azure-devops-services-agent"></a>Agente di Azure DevOps Services

* [Immagini dell'agente di Azure DevOps Services in DockerHub](https://hub.docker.com/r/microsoft/vsts-agent/)

* [Immagini dell'agente di Azure DevOps Services in GitHub](https://github.com/Microsoft/vsts-agent-docker)

#### <a name="operations-management-suite-oms-linux-agent"></a>Agente Operations Management Suite (OMS) per Linux

* [Operations Management Suite (OMS) Linux agent overview](https://github.com/Microsoft/OMS-Agent-for-Linux/blob/master/docs/Docker-Instructions.md) (Panoramica dell'agente Operations Management Suite (OMS) per Linux)

* [Operations Management Suite (OMS) images on DockerHub](https://hub.docker.com/r/microsoft/oms/) (Immagini Operations Management Suite (OMS) in DockerHub)

* [Operations Management Suite (OMS) images on GitHub](https://github.com/Microsoft/OMS-docker) (Immagini Operations Management Suite (OMS) in GitHub)

#### <a name="microsoft-azure-command-line-interface-cli"></a>Interfaccia della riga di comando di Microsoft Azure

* [Microsoft Azure Command Line Interface (CLI) images on DockerHub](https://hub.docker.com/r/microsoft/azure-cli/) (Immagini dell'interfaccia della riga di comando di Microsoft Azure in DockerHub) 

* [Microsoft Azure Command Line Interface (CLI) images on GitHub](https://github.com/Azure/azure-cli#Docker) (Immagini dell'interfaccia della riga di comando di Microsoft Azure in GitHub)

> [!NOTE]
> Se non si ha una sottoscrizione di Azure, [iscriversi subito](https://azure.microsoft.com/free/?b=16.48) per ottenere un account gratuito di 30 giorni e 200 dollari in crediti di Azure per poter provare una combinazione dei servizi di Azure.

#### <a name="microsoft-azure-cosmos-db-emulator-windows-containers-only"></a>Emulatore di Microsoft Azure Cosmos DB (solo contenitori Windows)

* [Microsoft Azure Cosmos DB Emulator images on DockerHub](https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator) (Immagini dell'emulatore di Microsoft Azure Cosmos DB in DockerHub) 

* [Use the Azure Cosmos DB Emulator for local development and testing](/azure/cosmos-db/local-emulator#developing-with-the-emulator) (Usare l'emulatore di Azure Cosmos DB per sviluppo e test locali)

## <a name="exploring-the-rich-docker-development-ecosystem"></a>Esplorazione dell'ecosistema di sviluppo avanzato Docker

Ora che la piattaforma Docker e le diverse immagini Docker sono state illustrate , il passaggio successivo prevede l'esplorazione dell'avanzato ecosistema Docker. I collegamenti seguenti illustrano come gli strumenti Microsoft integrano lo sviluppo dei contenitori.

* [Using .NET and Docker together](https://blogs.msdn.microsoft.com/dotnet/2017/05/25/using-net-and-docker-together/) (Uso combinato di .NET e Docker)
* [Progettazione e sviluppo di applicazioni .NET basate su più contenitori e microservizi](../../standard/microservices-architecture/multi-container-microservice-net-applications/index.md)
* [Visual Studio Code Docker extension](https://code.visualstudio.com/docs/languages/dockerfile) (Estensione Docker di Visual Studio Code)
* [Learn how to use Azure Service Fabric](/azure/service-fabric/index) (Informazioni su come usare Azure Service Fabric)
* [Service Fabric Getting Started Sample](https://azure.microsoft.com/resources/samples/service-fabric-dotnet-getting-started/) (Esempio introduttivo su Service Fabric)
* [Benefits of Windows Containers](/virtualization/windowscontainers/about/index#video-overview) (Vantaggi dei contenitori Windows)
* [Working with Visual Studio Docker Tools](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Uso degli strumenti Docker per Visual Studio)
* [Deploying Docker Images from the Azure Container Registry to Azure Container Instances](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/) (Distribuzione di immagini Docker dal Registro contenitori di Azure a Istanze di contenitore di Azure)
* [Debugging with Visual Studio Code](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) (Debug con Visual Studio Code)
* [Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments) (Informazioni su Visual Studio per Mac, contenitori e codice senza server nel cloud)
* [Getting Started with Docker and Visual Studio for Mac Lab](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started) (Lab introduttivo per Docker e Visual Studio per Mac)

## <a name="next-steps"></a>Passaggi successivi

* [Apprendere le nozioni di base di Docker con .NET Core](docker-basics-dotnet-core.md)
* [Compilazione di immagini Docker per .NET Core](building-net-docker-images.md)
