---
title: Ambiente di sviluppo per le app di Docker
description: Ciclo di vita dell'applicazione nei contenitori Docker con strumenti e piattaforma Microsoft
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: eedba16136ad394bda45cc871944f9b876c8ee38
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2017
---
# <a name="development-environment-for-docker-apps"></a>Ambiente di sviluppo per le app di Docker

## <a name="development-tools-choices-ide-or-editor"></a>Gli strumenti di sviluppo scelte: IDE o editor

Indipendentemente dal fatto se si preferisce un IDE potente e completo o un editor di tipo semplice e agile, Microsoft ha la copertura per quanto riguarda lo sviluppo di applicazioni di Docker.

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a>Visual Studio Code e Docker CLI (strumenti multipiattaforma per Mac, Linux e Windows)

Se si preferisce un editor leggero, multipiattaforma supportare qualsiasi linguaggio di sviluppo, è possibile utilizzare codice di Visual Studio e CLI di Docker. Questi prodotti forniscono un'esperienza semplice ed efficace, è fondamentale per semplificare il flusso di lavoro di sviluppo. Installando "Docker per Mac" o "Docker per Windows" (development environment), gli sviluppatori di Docker possono utilizzare un singolo CLI di Docker per creare App per Windows o Linux (ambiente di runtime) per. Inoltre, codice di Visual Studio supporta le estensioni per Docker con IntelliSense per i Dockerfile e le attività di scelta rapida eseguire i comandi di Docker dall'editor.

> [!NOTE]
> Per scaricare codice di Visual Studio, visitare <https://code.visualstudio.com/download>.

Per scaricare Docker per Mac e Windows, visitare <http://www.docker.com/products/docker>.

### <a name="visual-studio-with-docker-tools"></a>Visual Studio con strumenti di Docker

Quando si utilizza Visual Studio 2015 è possibile installare gli strumenti di componente aggiuntivo "Strumenti di Docker per Visual Studio". Per Visual Studio 2017, strumenti di Docker provenire incorporati già. In entrambi i casi che è possibile sviluppare, eseguire e convalidare le applicazioni direttamente nell'ambiente di Docker scelto. F5 (singolo contenitore o più contenitori) l'applicazione direttamente in una Docker host con il debug oppure premere Ctrl + F5 per modificare e aggiornare l'app senza dover ricompilare il contenitore. Questa è la scelta più semplice e più potente per gli sviluppatori di Windows, la creazione di contenitori di Docker per Linux o Windows.

> [!NOTE]
> Per scaricare gli strumenti di Docker per Visual Studio, visitare <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.

## <a name="language-and-framework-choices"></a>Opzioni di lingua e framework

È possibile sviluppare applicazioni di Docker e gli strumenti di Microsoft con i linguaggi più recenti. Di seguito è riportato un elenco iniziale, ma non si è limitati a esso:

-   .NET core e ASP.NET Core

-   Node.js

-   Golang

-   Java

-   Ruby

-   Python

In pratica, è possibile utilizzare un moderno linguaggio supportato da Docker in Linux o Windows.


>[!div class="step-by-step"]
[Precedente] (orchestrare-elevata-scalabilità-availability.md) [Avanti] (docker-App-interna-loop-workflow.md)
