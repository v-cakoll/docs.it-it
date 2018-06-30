---
title: Ambiente di sviluppo per le app di Docker
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 3da7816127982c3657129561975eed6d1f5aad5a
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37104507"
---
# <a name="development-environment-for-docker-apps"></a>Ambiente di sviluppo per le app di Docker

## <a name="development-tools-choices-ide-or-editor"></a>Opzioni degli strumenti di sviluppo: IDE o editor

Indipendentemente dal fatto se si preferisce un IDE potente e completo o un editor semplice e agile, Microsoft ha è coperto per quanto riguarda lo sviluppo di applicazioni di Docker.

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a>Visual Studio Code e Docker CLI (strumenti multipiattaforma per Mac, Linux e Windows)

Se si preferisce un editor leggero, multipiattaforma supportare qualsiasi linguaggio di sviluppo, è possibile utilizzare Visual Studio Code e CLI di Docker. Questi prodotti forniscono un'esperienza semplice ed efficace, è fondamentale per semplificare il flusso di lavoro di sviluppo. Installando "Docker per Mac" o "Docker per Windows" (development environment), gli sviluppatori di Docker possono utilizzare un singolo CLI di Docker per compilare App per Windows o Linux (ambiente di runtime). Inoltre, codice di Visual Studio supporta le estensioni per Docker con IntelliSense per i Dockerfile e le attività di scelta rapida eseguire i comandi di Docker dall'editor.

> [!NOTE]
> Per scaricare codice di Visual Studio, visitare <https://code.visualstudio.com/download>.

Per scaricare Docker per Mac e Windows, visitare <https://www.docker.com/products/docker>.

### <a name="visual-studio-with-docker-tools"></a>Visual Studio con gli strumenti di Docker

Quando si utilizza Visual Studio 2015 è possibile installare gli strumenti di componente aggiuntivo "Docker Tools per Visual Studio". Per Visual Studio 2017, strumenti di Docker provenire incorporati già. In entrambi i casi che è possibile sviluppare, eseguire e convalidare le applicazioni direttamente nell'ambiente di Docker scelto. F5 applicazione (singolo contenitore o più contenitori) direttamente in una Docker host con il debug oppure premere Ctrl + F5 per modificare e aggiornare l'app senza dover ricompilare il contenitore. Questa è la scelta più semplice e più potente per gli sviluppatori di Windows, la creazione di contenitori di Docker per Windows o Linux.

> [!NOTE]
> Per scaricare gli strumenti di Docker per Visual Studio, visitare <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.

## <a name="language-and-framework-choices"></a>Opzioni di lingua e framework

È possibile sviluppare applicazioni di Docker e gli strumenti di Microsoft con i linguaggi più recenti. È riportato un elenco iniziale, ma non si è limitati a esso:

-   .NET core e ASP.NET Core
-   Node.js
-   Golang
-   Java
-   Ruby
-   Python

In pratica, è possibile utilizzare un moderno linguaggio supportato da Docker in Windows o Linux.


>[!div class="step-by-step"]
[Precedente](orchestrate-high-scalability-availability.md)
[Successivo](docker-apps-inner-loop-workflow.md)
