---
title: Processo di sviluppo per le applicazioni basate su Docker
description: Ottenere una panoramica di alto livello delle opzioni per lo sviluppo di applicazioni basate su Docker. Uso di Visual Studio per Windows, Visual Studio per Mac o Visual Studio Code per il supporto multipiattaforma (Windows, macOS e Linux).
ms.date: 01/30/2020
ms.openlocfilehash: 799aa6fc742a8fb763ec5a7ae3cf3f70f89bed6d
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77502723"
---
# <a name="development-process-for-docker-based-applications"></a>Processo di sviluppo per le applicazioni basate su Docker

*Sviluppare applicazioni .NET in contenitori nel modo desiderato, l'ambiente di sviluppo integrato (IDE) con Visual Studio e gli strumenti di Visual Studio per Docker o l'interfaccia della riga di comando e l'editor con interfaccia della riga di comando di Docker e Visual Studio Code.*

## <a name="development-environment-for-docker-apps"></a>Ambiente di sviluppo per le app di Docker

### <a name="development-tool-choices-ide-or-editor"></a>Strumenti di sviluppo: IDE o editor

Microsoft include strumenti che è possibile usare per lo sviluppo di applicazioni di Docker, sia se si sceglie un IDE potente e completo che con un editor semplice e agile.

**Visual Studio (per Windows).** Per lo sviluppo di applicazioni .NET Core 3,1 basate su Docker con Visual Studio è necessario Visual Studio 2019 versione 16,4 o successiva. Visual Studio 2019 è dotato di strumenti per Docker già integrato. Gli strumenti per Docker consentono di sviluppare, eseguire e convalidare le applicazioni direttamente nell'ambiente di Docker di destinazione. È possibile premere F5 per eseguire l'applicazione ed eseguirne il debug (con contenitore singolo o più contenitori) direttamente in un host Docker oppure premere CTRL + F5 per modificare e aggiornare l'applicazione senza dovere ricompilare il contenitore. Questa è la scelta di sviluppo più potente per le app basate su Docker.

**Visual Studio per Mac.** Si tratta di un IDE, evoluzione di Xamarin Studio, in esecuzione in macOS. Per lo sviluppo di .NET Core 3,1, è richiesta la versione 8,4 o successiva. Questa deve essere la scelta migliore per gli sviluppatori che lavorano in computer macOS che vogliono usare anche un IDE potente.

**Visual Studio Code e CLI di Docker**. Se si preferisce un editor leggero e multipiattaforma che supporta qualsiasi linguaggio di sviluppo, è possibile usare Visual Studio Code e l'interfaccia della riga di comando di Docker. Si tratta di un approccio di sviluppo multipiattaforma per macOS, Linux e Windows. Inoltre, Visual Studio Code supporta le estensioni per Docker, quali IntelliSense per Dockerfile e le attività collegamento per eseguire i comandi di Docker dall'editor.

Installando [Docker Desktop Community Edition (CE)](https://hub.docker.com/search/?type=edition&offering=community), è possibile usare una singola interfaccia della riga di comando di Docker per creare app per Windows e Linux.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Visual Studio**. Sito ufficiale. \
  [https://visualstudio.microsoft.com/vs/](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)

- **Visual Studio Code**. Sito ufficiale. \
  <https://code.visualstudio.com/download>

- **Docker Desktop per Windows Community Edition (CE)**  \
  [https://hub.docker.com/editions/community/docker-ce-desktop-windows](https://hub.docker.com/editions/community/docker-ce-desktop-windows)

- **Docker Desktop per Mac Community Edition (CE)**  \
  [https://hub.docker.com/editions/community/docker-ce-desktop-mac](https://hub.docker.com/editions/community/docker-ce-desktop-mac)

## <a name="net-languages-and-frameworks-for-docker-containers"></a>Linguaggi e framework .NET per contenitori di Docker

Come indicato nelle sezioni precedenti di questa guida, è possibile usare .NET Framework, .NET Core o il progetto Mono open source per lo sviluppo di applicazioni .NET incluse in contenitori di Docker. È possibile sviluppare in C\#, F\# o Visual Basic quando si usano contenitori di Linux o Windows, a seconda del framework .NET in uso. Per altri dettagli sui linguaggi .NET, vedere il post di blog [The .NET Language Strategy (La strategia dei linguaggi .NET)](https://devblogs.microsoft.com/dotnet/the-net-language-strategy/).

>[!div class="step-by-step"]
>[Precedente](../architect-microservice-container-applications/scalable-available-multi-container-microservice-applications.md)
>[Successivo](docker-app-development-workflow.md)
