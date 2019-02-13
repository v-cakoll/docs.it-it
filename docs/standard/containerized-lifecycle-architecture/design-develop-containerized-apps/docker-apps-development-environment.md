---
title: Ambiente di sviluppo per le app di Docker
description: Conoscere i più importanti opzioni dello strumento di sviluppo che supportano il ciclo di vita di sviluppo Docker.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: 1d22b45a8eee9198d337df9f0b8b4b78371fa31a
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219997"
---
# <a name="development-environment-for-docker-apps"></a>Ambiente di sviluppo per le app di Docker

## <a name="development-tools-choices-ide-or-editor"></a>Strumenti di sviluppo possibili: IDE o editor

Non importa se si preferisce un IDE potente e completo o un editor semplice e agile, Microsoft ha ti serve se si desidera lo sviluppo di applicazioni di Docker.

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a>Visual Studio Code e CLI di Docker (strumenti multipiattaforma per Mac, Linux e Windows)

Se si preferisce un editor leggero e multipiattaforma che supporta qualsiasi linguaggio di sviluppo, è possibile usare Visual Studio Code e CLI di Docker. Questi prodotti forniscono un'esperienza semplice ma efficace, di fondamentale importanza per semplificare il flusso di lavoro per gli sviluppatori. Tramite l'installazione di "Docker per Mac" o "Docker per Windows" (development environment), gli sviluppatori Docker possono usare una singola interfaccia CLI di Docker per creare App per Windows o Linux (ambiente di runtime). Inoltre, Visual Studio Code supporta le estensioni per Docker con IntelliSense per Dockerfile e le attività di collegamento eseguire i comandi di Docker dall'editor.

> [!NOTE]
> Per scaricare Visual Studio Code, visitare <https://code.visualstudio.com/download>.

Per scaricare Docker per Mac e Windows, visitare <https://www.docker.com/products/docker>.

### <a name="visual-studio-with-docker-tools"></a>Visual Studio con gli strumenti di Docker

Quando si usa Visual Studio 2015 è possibile installare gli strumenti di componente aggiuntivo "Docker Tools per Visual Studio". Per Visual Studio 2017, gli strumenti di Docker vengono incorporati già. In entrambi i casi che è possibile sviluppare, eseguire e convalidare le applicazioni direttamente nell'ambiente Docker selezionato. F5 l'applicazione (con contenitore singolo o più contenitori) direttamente in un Docker ospitare con il debug oppure premere CTRL+F5 per modificare e aggiornare l'app senza dovere ricompilare il contenitore. Questa è la scelta più semplice e più potente per gli sviluppatori Windows la creazione di contenitori Docker per Linux o Windows.

> [!NOTE]
> Per scaricare gli strumenti di Docker per Visual Studio, passare a <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>.

## <a name="language-and-framework-choices"></a>Opzioni relative a lingua e framework

È possibile sviluppare applicazioni di Docker e gli strumenti di Microsoft con i linguaggi più moderni. Di seguito è riportato un elenco iniziale, ma non si è limitati a esso:

-   .NET Core e ASP.NET Core
-   Node.js
-   Golang
-   Java
-   Ruby
-   Python

In pratica, è possibile usare qualsiasi linguaggio moderno supportato da Docker in Linux o Windows.

>[!div class="step-by-step"]
>[Precedente](deploy-azure-kubernetes-service.md)
>[Successivo](docker-apps-inner-loop-workflow.md)