---
title: Ambiente di sviluppo per le app di Docker
description: Informazioni sulle opzioni più importanti dello strumento di sviluppo che supportano il ciclo di vita di sviluppo Docker.
ms.date: 02/15/2019
ms.openlocfilehash: 35236e75f47e830d0970ca9cfd074d9a69e6f85c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "71214298"
---
# <a name="development-environment-for-docker-apps"></a>Ambiente di sviluppo per le app di Docker

## <a name="development-tools-choices-ide-or-editor"></a>Opzioni degli strumenti di sviluppo: IDE o editor

Indipendentemente dal fatto che si preferisca usare un IDE completo e potente o un editor leggero e flessibile, Microsoft offre tutti gli strumenti necessari per lo sviluppo delle applicazioni Docker.

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a>Visual Studio Code e interfaccia della riga di comando di Docker (strumenti multipiattaforma per Mac, Linux e Windows)

Se si preferisce un editor leggero e multipiattaforma che supporta qualsiasi linguaggio di sviluppo, è possibile usare Visual Studio Code e l'interfaccia della riga di comando di Docker. Questi prodotti offrono un'esperienza semplice ed efficace che consente di ottimizzare il flusso di lavoro di sviluppo. Installando "Docker per Mac" o "Docker per Windows" (ambiente di sviluppo), gli sviluppatori Docker possono usare una singola interfaccia della riga di comando di Docker per creare app per Windows o Linux (ambiente di runtime). Inoltre, Visual Studio Code supporta le estensioni per Docker con IntelliSense per Dockerfile e le attività collegamento per eseguire i comandi Docker dall'editor.

> [!NOTE]
> Per scaricare Visual Studio Code, visitare <https://code.visualstudio.com/download>.
>
> Per scaricare Docker per Mac e Windows, visitare <https://www.docker.com/products/docker>.

### <a name="visual-studio-with-docker-tools-windows-development-machine"></a>Visual Studio con strumenti Docker (computer di sviluppo Windows)

Si consiglia di usare Visual Studio 2017 (o versione successiva) con gli strumenti Docker incorporati abilitati. Con Visual Studio è possibile sviluppare, eseguire e convalidare le applicazioni direttamente nell'ambiente Docker selezionato. Premere F5 per eseguire il debug dell'applicazione (con contenitore singolo o più contenitori) direttamente in un host Docker oppure premere CTRL+F5 per modificare e aggiornare l'applicazione senza dovere ricompilare il contenitore. Questa è la soluzione più semplice ed efficace per gli sviluppatori di Windows per creare contenitori di Docker per Linux o Windows.

### <a name="visual-studio-for-mac-mac-development-machine"></a>Visual Studio per Mac (computer di sviluppo Mac)

È possibile usare [Visual Studio per Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) per lo sviluppo di applicazioni basate su Docker. Visual Studio per Mac offre un ambiente IDE più avanzato rispetto a Visual Studio Code per Mac.

## <a name="language-and-framework-choices"></a>Linguaggio e framework

È possibile sviluppare applicazioni Docker con gli strumenti Microsoft con i linguaggi più moderni. L'elenco riportato di seguito è un elenco iniziale non completo:

- .NET Core e ASP.NET Core
- Node.js
- Go
- Java
- Ruby
- Python

In pratica, è possibile usare qualsiasi linguaggio moderno supportato da Docker in Linux o Windows.

>[!div class="step-by-step"]
>[Successivo](deploy-azure-kubernetes-service.md)
>[precedente](docker-apps-inner-loop-workflow.md)
