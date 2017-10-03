---
title: Processo di sviluppo per le applicazioni basate su Docker
description: Architettura di microservizi .NET per le applicazioni .NET incluse in contenitori | Processo di sviluppo per le applicazioni basate su Docker
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.translationtype: HT
ms.sourcegitcommit: 9bb64ea7199f5699ff166d1affb7f8126dcc6612
ms.openlocfilehash: f4c241f463ff1270037c7d66ba39409ca5d9e728
ms.contentlocale: it-it
ms.lasthandoff: 09/05/2017

---
# <a name="development-process-for-docker-based-applications"></a>Processo di sviluppo per le applicazioni basate su Docker

*È possibile sviluppare applicazioni .NET incluse in contenitori come si preferisce, sia basandosi su IDE con Visual Studio e Visual Studio Tools per Docker oppure su editor/CLI con CLI di Docker e Visual Studio Code.*

## <a name="development-environment-for-docker-apps"></a>Ambiente di sviluppo per le app di Docker

### <a name="development-tool-choices-ide-or-editor"></a>Strumenti di sviluppo: IDE o editor

Microsoft include strumenti che è possibile usare per lo sviluppo di applicazioni di Docker, sia se si sceglie un IDE potente e completo che con un editor semplice e agile.

**Visual Studio Tools per Docker**. Se si usa Visual Studio 2015, è possibile installare il componente aggiuntivo [Visual Studio Tools per Docker](https://marketplace.visualstudio.com/items?itemName=MicrosoftCloudExplorer.VisualStudioToolsforDocker-Preview). Se si usa Visual Studio 2017, gli strumenti per Docker sono già incorporati. In entrambi i casi, gli strumenti per Docker consentono di sviluppare, eseguire e convalidare le applicazioni direttamente nell'ambiente di Docker di destinazione. È possibile premere F5 per eseguire l'applicazione ed eseguirne il debug (con contenitore singolo o più contenitori) direttamente in un host Docker oppure premere CTRL + F5 per modificare e aggiornare l'applicazione senza dovere ricompilare il contenitore. Questa è la soluzione più semplice ed efficace per gli sviluppatori di Windows che usano contenitori di Docker per Linux o Windows.

**Visual Studio Code e CLI di Docker**. Se si preferisce un editor leggero e multipiattaforma che supporta qualsiasi linguaggio di sviluppo, è possibile usare Microsoft Visual Studio Code (codice Visual Studio) e l'interfaccia CLI di Docker. Questo approccio di sviluppo multipiattaforma è adatto per Mac, Linux e Windows.

Questi prodotti forniscono un'esperienza semplice ma efficace che consente di ottimizzare il flusso di lavoro di sviluppo. Installando gli strumenti di [Docker Community Edition (CE)](https://www.docker.com/community-edition), è possibile usare un'interfaccia CLI di Docker singola per creare app per Windows e Linux. Inoltre, Visual Studio Code supporta le estensioni per Docker, quali IntelliSense per Dockerfile e le attività collegamento per eseguire i comandi di Docker dall'editor.

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Visual Studio Tools per Docker**
    [*https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4*](https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4)

-   **Visual Studio Code**. Sito ufficiale.
    [*https://code.visualstudio.com/download*](https://code.visualstudio.com/download)

-   **Docker Community Edition (CE) per Mac e Windows**
    [*https://www.docker.com/community-editions*](https://www.docker.com/community-edition)

## <a name="net-languages-and-frameworks-for-docker-containers"></a>Linguaggi e framework .NET per contenitori di Docker

Come indicato nelle sezioni precedenti di questa guida, è possibile usare .NET Framework, .NET Core o il progetto Mono open source per lo sviluppo di applicazioni .NET incluse in contenitori di Docker. È possibile sviluppare in C\#, F\# o Visual Basic quando si usano contenitori di Linux o Windows, a seconda del framework .NET in uso. Per altri dettagli sui linguaggi .NET, vedere il post di blog [The .NET Language Strategy (La strategia dei linguaggi .NET)](https://blogs.msdn.microsoft.com/dotnet/2017/02/01/the-net-language-strategy/).


>[!div class="step-by-step"]
[Precedente] (../architect-microservice-container-applications/using-azure-service-fabric.md) [Successivo] (docker-app-development-workflow.md)

