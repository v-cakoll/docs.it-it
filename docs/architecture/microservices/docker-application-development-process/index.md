---
title: Processo di sviluppo per applicazioni basate su Docker
description: Ottieni una panoramica generale delle opzioni per lo sviluppo di applicazioni basate su Docker. Uso di Visual Studio per Windows, Visual Studio per Mac o Visual Studio Code per il supporto multipiattaforma (Windows, macOS e Linux).
ms.date: 01/30/2020
ms.openlocfilehash: 799aa6fc742a8fb763ec5a7ae3cf3f70f89bed6d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "77502723"
---
# <a name="development-process-for-docker-based-applications"></a>Processo di sviluppo per applicazioni basate su Docker

*Sviluppare applicazioni .NET containerizzate nel modo desiderato, oppure con Visual Studio (Integrated Development Environment) incentrate su Visual Studio e gli strumenti di Visual Studio per Docker o CLI/Editor incentrati su Docker CLI e Visual Studio Code.*

## <a name="development-environment-for-docker-apps"></a>Ambiente di sviluppo per le app di Docker

### <a name="development-tool-choices-ide-or-editor"></a>Strumenti di sviluppo: IDE o editor

Microsoft include strumenti che è possibile usare per lo sviluppo di applicazioni di Docker, sia se si sceglie un IDE potente e completo che con un editor semplice e agile.

**Visual Studio (per Windows).** Lo sviluppo di applicazioni .NET Core 3.1 basato su Docker con Visual Studio richiede Visual Studio 2019 versione 16.4 o successiva. Visual Studio 2019 include strumenti per Docker già integrati. Gli strumenti per Docker consentono di sviluppare, eseguire e convalidare le applicazioni direttamente nell'ambiente di Docker di destinazione. È possibile premere F5 per eseguire l'applicazione ed eseguirne il debug (con contenitore singolo o più contenitori) direttamente in un host Docker oppure premere CTRL + F5 per modificare e aggiornare l'applicazione senza dovere ricompilare il contenitore. Questa è la scelta di sviluppo più potente per le app basate su Docker.

**Visual Studio per Mac.** È un IDE, l'evoluzione di Xamarin Studio, in esecuzione in macOS. Per lo sviluppo di .NET Core 3.1, richiede la versione 8.4 o successiva. Questa dovrebbe essere la scelta preferita per gli sviluppatori che lavorano in macchine macOS che vogliono anche utilizzare un potente IDE.

**Visual Studio Code e CLI di Docker**. Se si preferisce un editor leggero e multipiattaforma che supporta qualsiasi linguaggio di sviluppo, è possibile utilizzare Visual Studio Code e l'interfaccia della riga di comando Docker.If you prefer a lightweight and cross-platform editor that supports any development language, you can use Visual Studio Code and the Docker CLI. Si tratta di un approccio di sviluppo multipiattaforma per macOS, Linux e Windows. Inoltre, Visual Studio Code supporta le estensioni per Docker, quali IntelliSense per Dockerfile e le attività collegamento per eseguire i comandi di Docker dall'editor.

Installando [Docker Desktop Community Edition (CE)](https://hub.docker.com/search/?type=edition&offering=community), è possibile usare una singola interfaccia della riga di comando di Docker per creare app per Windows e Linux.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Visual Studio**. Sito ufficiale. \
  [https://visualstudio.microsoft.com/vs/](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)

- **Codice di Visual Studio**. Sito ufficiale. \
  <https://code.visualstudio.com/download>

- **Docker Desktop for Windows Community Edition (CE)** \
  [https://hub.docker.com/editions/community/docker-ce-desktop-windows](https://hub.docker.com/editions/community/docker-ce-desktop-windows)

- **Docker Desktop per Mac Community Edition (CE)** \
  [https://hub.docker.com/editions/community/docker-ce-desktop-mac](https://hub.docker.com/editions/community/docker-ce-desktop-mac)

## <a name="net-languages-and-frameworks-for-docker-containers"></a>Linguaggi e framework .NET per contenitori di Docker

Come indicato nelle sezioni precedenti di questa guida, è possibile usare .NET Framework, .NET Core o il progetto Mono open source per lo sviluppo di applicazioni .NET incluse in contenitori di Docker. È possibile sviluppare in C\#, F\# o Visual Basic quando si usano contenitori di Linux o Windows, a seconda del framework .NET in uso. Per altri dettagli sui linguaggi .NET, vedere il post di blog [The .NET Language Strategy (La strategia dei linguaggi .NET)](https://devblogs.microsoft.com/dotnet/the-net-language-strategy/).

>[!div class="step-by-step"]
>[Successivo](../architect-microservice-container-applications/scalable-available-multi-container-microservice-applications.md)
>[precedente](docker-app-development-workflow.md)
