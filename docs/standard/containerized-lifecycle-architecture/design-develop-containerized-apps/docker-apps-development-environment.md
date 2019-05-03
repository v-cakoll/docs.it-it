---
title: Ambiente di sviluppo per le app di Docker
description: Conoscere i più importanti opzioni dello strumento di sviluppo che supportano il ciclo di vita di sviluppo Docker.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 3a2fcbe3b9380083622b6ce72cea4bab17d7c2ea
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61799320"
---
# <a name="development-environment-for-docker-apps"></a>Ambiente di sviluppo per le app di Docker

## <a name="development-tools-choices-ide-or-editor"></a>Strumenti di sviluppo possibili: IDE o editor

Non importa se si preferisce un IDE potente e completo o un editor semplice e agile, Microsoft ha ti serve se si desidera lo sviluppo di applicazioni di Docker.

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a>Visual Studio Code e CLI di Docker (strumenti multipiattaforma per Mac, Linux e Windows)

Se si preferisce un editor leggero e multipiattaforma che supporta qualsiasi linguaggio di sviluppo, è possibile usare Visual Studio Code e CLI di Docker. Questi prodotti forniscono un'esperienza semplice ma efficace, di fondamentale importanza per semplificare il flusso di lavoro per gli sviluppatori. Tramite l'installazione di "Docker per Mac" o "Docker per Windows" (development environment), gli sviluppatori Docker possono usare una singola interfaccia CLI di Docker per creare App per Windows o Linux (ambiente di runtime). Inoltre, Visual Studio Code supporta le estensioni per Docker con IntelliSense per Dockerfile e le attività di collegamento eseguire i comandi di Docker dall'editor.

> [!NOTE]
>
> Per scaricare Visual Studio Code, visitare <https://code.visualstudio.com/download>.
>
> Per scaricare Docker per Mac e Windows, visitare <https://www.docker.com/products/docker>.

### <a name="visual-studio-with-docker-tools-windows-development-machine"></a>Visual Studio con gli strumenti di Docker (computer di sviluppo Windows)

È consigliabile usare Visual Studio 2017 (o versione successiva) con gli strumenti di Docker predefinita abilitata. Con Visual Studio, è possibile sviluppare, eseguire e convalidare le applicazioni direttamente nell'ambiente Docker selezionato. Premere F5 per eseguire il debug dell'applicazione (con contenitore singolo o più contenitori) direttamente in un host Docker oppure premere CTRL+F5 per modificare e aggiornare l'app senza dovere ricompilare il contenitore. È la scelta più semplice e più potente per gli sviluppatori di Windows creare i contenitori Docker per Linux o Windows.

### <a name="visual-studio-for-mac-mac-development-machine"></a>Visual Studio per Mac (computer di sviluppo Mac)

È possibile usare [Visual Studio per Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) durante lo sviluppo di applicazioni basate su Docker. Visual Studio per Mac offre un ambiente IDE più avanzato rispetto a Visual Studio Code per Mac.

## <a name="language-and-framework-choices"></a>Opzioni relative a lingua e framework

È possibile sviluppare applicazioni Docker con strumenti di Microsoft con i linguaggi più moderni. Di seguito è riportato un elenco iniziale, ma non è necessario limitarsi a esso:

- .NET Core e ASP.NET Core
- Node.js
- Vai
- Java
- Ruby
- Python

In pratica, è possibile usare qualsiasi linguaggio moderno supportato da Docker in Linux o Windows.

>[!div class="step-by-step"]
>[Precedente](deploy-azure-kubernetes-service.md)
>[Successivo](docker-apps-inner-loop-workflow.md)
